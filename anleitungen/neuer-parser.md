# Neuer Parser

Parser, oder im Kontext von Mocks Results genannt, werden als Unterklasse der `ToolResults` Klasse implementiert. Das Grundgerüst dieser Klasse besteht daraus, dass es ein Projekt Objekt übergeben bekommt, daraus notwendige Daten bezieht (wie bspw. Nessus Scan ID, Bloodhound Datenbank, Acunetix Report), diese wenn notwendig verarbeitet oder aufbereitet und sie über eine zentrale Funktion den Kapiteln zur Verfügung stellt.

## Erstellen der Klasse

### Definieren einer Konstanten

Zuallererst muss eine neue Konstante definiert werden. Diese wird verwendet um die Ergebnisse zu speichern und um auf sie zuzugreifen.&#x20;

In `config/settings.py` wird die `TOOL` Klasse um diese Konstante erweitert:

![](<../.gitbook/assets/image (12).png>)

### Erstellen der Datei

Danach kann eine neue Datei für die Klasse unter `mocks/results/tools` angelegt werden:

![](<../.gitbook/assets/image (3).png>)

### Implementierung der Klasse

Nun kann die Basis der neuen Klasse implementiert werden. Sie erbt von `ToolResults` und muss folgende Kriterien erfüllen:

* Die Klassenvariable `tool` muss auf die zu Beginn definierte Konstante gesetzt werden
* Die `__init__` Methode muss implementiert werden und ein Projekt als Argument erhalten
* Die `filter` Methode muss implementiert werden

Die dafür notwendigen Klassen können direkt von `mocks.results.base` importiert werden. Die leere Klasse würde demnach wie folgt aussehen:

![](<../.gitbook/assets/image (11).png>)

Unterklassen von `ToolResults` werden vom `ToolResultsManager` automatisch erkannt und geladen.

Vorher waren es nur zwei Unterklassen (Nessus und Bloodhound), jetzt sind es drei:

![](<../.gitbook/assets/image (10).png>)

Die Klasse würde beim Erstellen eines Berichts nun bereits aufgerufen und instanziiert werden.&#x20;

## Erweitern des Projekt Modells

Das Project Model speichert die relevanten Daten zur Erstellung eines Berichts. Es ist mehr oder weniger eine Abstraktion für die Daten, die in der Datenbank gespeichert sind. Zum Beispiel hat es ein `PositiveIntegerField` für eine Nessus-Scan-ID und einen `ForeignKey` für ein Bloodhound-Datenbankobjekt.

{% embed url="https://docs.djangoproject.com/en/4.0/topics/db/models/" %}

### Hinzufügen eines neuen Feldes

Unser neuer Acunetix Parser soll einen HTML-Report (also eine Datei) als Input verwenden. Daher müssen wir das Project Model um ein `FileField` erweitern, in dem der Bericht gespeichert wird.

{% embed url="https://docs.djangoproject.com/en/4.0/ref/models/fields/#filefield" %}

Datenbankmodelle werden immer in der jeweiligen `models.py` Datei angelegt. Das Project Model ist Teil der "projects" app:

![](<../.gitbook/assets/image (13).png>)

Nun erweitern wir das Model um das eben genannte Feld:

{% hint style="info" %}
Das Hochladen des Reports soll optional sein, deswegen setzen wir null und blank:

* [null](https://docs.djangoproject.com/en/4.0/ref/models/fields/#null) - dieses Feld darf in der Datenbank NULL sein
* [blank](https://docs.djangoproject.com/en/4.0/ref/models/fields/#null) - dieses Feld darf leer sein (betrifft bspw. Forms)
{% endhint %}

![](<../.gitbook/assets/image (6).png>)

{% hint style="warning" %}
Damit haben wir das Datenbankmodell geändert. Wenn wir Mocks einfach ausführen und Project Objekte verwenden, wird es Fehler geben. Das liegt daran, dass das neu erstellte `FileField` noch nicht in der eigentlichen Datenbank existiert und bestehende Projekte noch nicht migriert wurden.
{% endhint %}

### Erstellen und Anwenden der Datenbankmigrationen

Um eine Datenbankmigrationsdatei für diese Änderung zu erstellen, führen wir den folgenden Befehl aus:

![](<../.gitbook/assets/image (21).png>)

Diese Migrationen müssen auch angewandt werden:

![](<../.gitbook/assets/image (5).png>)

### Erweitern der Formulare

Django verwendet Forms, um neue Modellinstanzen zu erstellen oder bestehende zu aktualisieren. Diese Forms werden typischerweise in einer `forms.py` Datei gespeichert und von der jeweiligen View in `views.py` referenziert. Mocks verwendet außerdem das crispy-forms Plugin, um die Layouts der Forms anzupassen.

{% embed url="https://docs.djangoproject.com/en/4.0/topics/forms/" %}

{% embed url="https://django-crispy-forms.readthedocs.io/en/latest/" %}

Die Forms zum Erstellen und Aktualisieren von Projekten verwenden ein gemeinsames Basislayout. Wir erstellen ein neues Element, das auf das vorhin erstellte Feld mit seinem Namen referenziert:

{% hint style="info" %}
Siehe [Bootstrap Grid System](https://getbootstrap.com/docs/5.2/layout/grid/) und [Crispy Forms Layout](https://django-crispy-forms.readthedocs.io/en/latest/api\_layout.html?highlight=column#layout.Column) als Referenz.
{% endhint %}

![](<../.gitbook/assets/image (8).png>)

Die Seite mit den Projektdetails verwendet ein normales Django HTML-Template.

{% embed url="https://docs.djangoproject.com/en/4.0/topics/templates/" %}

Wir erweitern die Tabelle um eine neue Zeile, die anzeigt, ob ein Acunetix Report existiert oder nicht:

{% hint style="info" %}
Standardmäßig würd \{{ project.acunetix\_report \}} entweder einen leeren String ausgeben, oder den Dateinamen des hochgeladenen Reports.

Wir verwenden den Filter [yesno](https://docs.djangoproject.com/en/4.0/ref/templates/builtins/#yesno), um stattdessen anzuzeigen, ob ein Report existiert, oder nicht.
{% endhint %}

![](<../.gitbook/assets/image (15).png>)

### Ergebnisse auf der Seite

Beim Erstellen eines neuen Projekts ist es jetzt möglich, einen Acunetix-Bericht hochzuladen

![](<../.gitbook/assets/image (16).png>)

Und bei den Projektdetails wird angezeigt, ob ein Bericht hochgeladen wurde oder nicht:

![](<../.gitbook/assets/image (2).png>)

## Implementierung der Funktionalität

### Signalisieren fehlender Daten

Nun kann die `AcunetixResults` Klasse über `project.acunetix_report` auf die Datei zugreifen. Es gibt jedoch keine Garantie dafür, dass ein bestimmtes Projekt auch einen Acunetix Scan besitzt. Aus diesem Grund ist es Aufgabe der Klasse (genauer der `__init__` Methode), festzustellen, ob sie tatsächlich Ergebnisse erzeugen kann.

Um anzuzeigen, dass die erforderlichen Daten fehlen, wird die `ToolDataMissing` Exception verwendet:&#x20;

![](<../.gitbook/assets/image (19).png>)

### Parsen der Daten

\<LINK ZU SEITE, DIE ACUNETIX OUTPUT ERKLÄRT>

Um den HTML-Bericht zu parsen, werden wir BeautifulSoup

![](<../.gitbook/assets/image (9).png>)



