# at 

apt-get install at

queue, examine or delete jobs for later execution

### 


```
at 05:30
```
Anschließend gibt man die gewünschten Befehle ein und schließt die Eingabe mit Strg + D ab.
#### 


## Übersichten, Tabellen und Referenzen 

| Befehl        | Beschreibung                                         |
|---------------|------------------------------------------------------|
| `atq`         | Listet **alle geplanten Jobs** im System (sofern du die entsprechenden Berechtigungen hast) mit den Ausführungszeiten. |
| `at -l`       | Listet nur die geplanten **Jobs des aktuellen Benutzers** mit den Ausführungszeiten. |
| `atrm <Job-ID>` | Entfernt den angegebenen Job aus der Warteschlange, basierend auf der **Job-ID**. Beispiel: `atrm 2` entfernt Job mit ID 2. |



