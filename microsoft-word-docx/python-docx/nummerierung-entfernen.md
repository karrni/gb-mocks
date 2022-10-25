# Nummerierung entfernen

Wenn in einer Formatvorlage die Nummerierung aktiviert ist, kann sie mit dem folgenden Code manuell für einen bestimmten Absatz entfernt werden:

```python
def remove_numbering(paragraph):
    paragraph._p.get_or_add_pPr().get_or_add_numPr().get_or_add_numId().val = 0
    paragraph._p.get_or_add_pPr().get_or_add_numPr().get_or_add_ilvl().val = 0
```

Der häufigste Anwendungsfall sind die Kapitel "Umgesetzte Maßnahmen", die direkt unter der eigentlichen Überschrift ein Banner mit derselben Formatvorlage haben:

![](<../../.gitbook/assets/image (6) (1).png>)

Andernfalls würde es wie folgt aussehen:

![](<../../.gitbook/assets/image (5) (1).png>)

### Referenz

{% embed url="https://github.com/python-openxml/python-docx/issues/25#issuecomment-400787031" %}
