# at 

queue, examine or delete jobs for later execution

## Installation 

```
apt-get install at
```

## Befehle für spätere ausführung planen

1. at mit ausführungzeit eingeben
2. Befehle eingeben
3. Strg + D ab.

```
at 05:30 <Enter>
at Thu Dec  4 05:30:00 2042
at> init 6 <Ctrl + d>
```

#### 


## Übersichten, Tabellen und Referenzen 

| Befehl        | Beschreibung                                         |
|---------------|------------------------------------------------------|
| `atq`         | Listet **alle geplanten Jobs** im System mit den Ausführungszeiten. |
| `at -l`       | Listet nur die geplanten **Jobs des aktuellen Benutzers** mit den Ausführungszeiten. |
| `atrm <Job-ID>` | Entfernt den angegebenen Job aus der Warteschlange, basierend auf der **Job-ID**. Beispiel: `atrm 2` entfernt Job mit ID 2. |
| `batch`  | |



