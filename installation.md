# Installation

## Voraussetzungen

### Konfiguration

Mocks wird mithilfe von Umgebungsvariablen konfiguriert. Diese können in der .env Datei angegeben werden, welche von docker-compose direkt geladen wird.

Die .env.example Datei kann als Referenz verwendet werden:

```bash
cp .env.example .env
```

### Textblöcke

Mocks benötigt das Textblock-Repository, um Dokumente zu erzeugen. Die docker-compose.yml Datei bindet den Ordner von `./data/textblocks` ein.

## Installation

Wenn diese Voraussetzungen erfüllt sind, können die Container automatisch mittels docker-compose erstellt und gestartet werden:

```bash
docker-compose up
```

Wenn alles erledigt ist, ist die Anwendung einsatzbereit. Standardmäßig läuft Mocks auf Port 8000.
