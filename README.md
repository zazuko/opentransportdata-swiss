# opentransportdata-swiss

Dieses Repository enthält Beispiele von SPARQL Queries für die Abfrage der opentransportdata der Schweiz.

Die Daten befinden sich auf [LINDAS](https://lindas.admin.ch/) in den folgenden beiden Named-Graphs:
- https://lindas.admin.ch/sbb/nova
- https://lindas.admin.ch/sbb/didok

SPARQL Endpoint URL: https://int.lindas.admin.ch/query


## VSCode SPARQL Notebook

Wir verwenden ein [Notebook plugin für VSCode](https://marketplace.visualstudio.com/items?itemName=Zazuko.sparql-notebook), welches speziell für SPARQL entwickelt wurde.

Notebook file: [nova.sparqlbook](nova.sparqlbook)

Die meisten Queries im Notebook sind in Files ausgelagert, diese Files befinden sich im Folder [SPARQL](./SPARQL/). Dies bringt u.a. Vorteile in der Versionierung.

[nova.sparqlbook.md](nova.sparqlbook.md) ist ein Markdown Export des Notebooks.

**Hinweis**: Falls Query Resultate auf der Karte visualisiert werden sollen, das [Web-UI](https://s.zazuko.com/B8Bw7f) verwenden.