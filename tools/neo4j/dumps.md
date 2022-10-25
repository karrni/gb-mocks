# Dumps

## Erstellen

Datenbankdumps können mithilfe des neo4j-admin Tools erstellt werden:

```
neo4j-admin dump --to=<PATH>
```

## Laden

Das Laden von Dumps ist ebenfalls mithilfe des neo4j-admin Tools möglich:

```
neo4j-admin load --from=<ARCHIVE> --database=<DATABASE> --force
```

Dieses Tool arbeitet jedoch nur mit dem lokalen Dateisystem. Das bedeutet, dass Dumps nicht remote geladen werden können. Da Django und Neo4j in separaten Containern laufen stellt das ein Problem dar
