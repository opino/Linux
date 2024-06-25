# Bash

- [Übersichten, Tabellen und Referenzen](#-bersichten--tabellen-und-referenzen)
  * [Tastatursteuerung](#tastatursteuerung)
  * [Rückgabewerte](#r-ckgabewerte)
  * [Bash Handbücher](#bash-handb-cher)
- [Initale Einstellungen](#initale-einstellungen)
  * [Alias](#alias)
  * [history](#history)
- [Bash Programierung](#bash-programierung)
  * [Tests](#tests)
      - [String Tests](#string-tests)
      - [Arithmetic Tests](#arithmetic-tests)  
  * [for](#for)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>




1. Übersichten, Tabellen und Referenzen
1. Inital Einstellungen
1. Bash Programierung

## Übersichten, Tabellen und Referenzen 
### Tastatursteuerung

|Tastenkürzel| abcde |
|---------|------------------|
| Strg-A	| Cursor am Zeilenanfang positionieren |
| Strg-E	| Cursor am Zeilenende positionieren |
| »Linker Pfeil« Strg-B	| Cursor, ohne zu löschen, ein Zeichen nach links bewegen|
| »Rechter Pfeil« Strg-F |	Cursor, ohne zu löschen, ein Zeichen nach rechts bewegen |
| DEL	| Das Zeichen links vom Cursor wird gelöscht |
| Strg-D	| Das Zeichen unter dem Cursor wird gelöscht |
| Strg-U |	Vom Cursor bis zum Zeilenanfang alle Zeichen löschen |
| Strg-K |	Vom Cursor bis zum Zeilenende alle Zeichen löschen |

Wortsteuerung:
|        | |
|-------|-------|

| Esc b | Ein Wort zurück bewegen |
| Esc f | 	Ein Wort vor bewegen |
| Esc DEL Strg-W	 |Das Wort links vom Cursor löschen |
| Esc d | 	Das Wort unter dem Cursor löschen |
| Strg-Y |	Das zuletzt gelöschte Wort zurückholen |

 Historysteuerung: 
|        | |
|-------|-------|
| »Pfeil nach oben« Strg-P|	Die vorherige Zeile zurückholen |
| »Pfeil nach unten« Strg-N | 	Die nächste Zeile zurückholen |
| Strg-R | 	Rückwärts suchen |
| Esc <	| Die erste Zeile der History hervorholen |
| Esc >	| Die letzte Zeile der History hervorholen |

 Zeichensteuerung: 
|        | |
|-------|-------|
| Strg-T	Vertauscht das unter dem Cursor stehende Zeichen mit seinem linken Nachbarn |
| Strg-V	Das nächste eingegebene Zeichen wird maskiert, d. h. seiner besonderen Bedeutung beraubt |

 Prozesssteuerung: 
|        | |
|-------|-------|
| Strg-C | 	Unterbricht das gerade laufende Kommando |
| Strg-S |	Bildschirmausgabe anhalten |
| Strg-Q |	Gehaltene Bildschirmausgabe fortsetzen |





### Rückgabewerte
```
$?    Rückgabe wert des letzten Befehls
```
### Bash Handbücher
1. https://tldp.org/LDP/abs/html/refcards.html#AEN22402
1. https://tldp.org/LDP/abs/html/
1. https://www-user.tu-chemnitz.de/~hot/unix_linux_werkzeugkasten/bash.html#testexpr
1. https://www.gnu.org/software/bash/manual/html_node/index.html#SEC_Contents

## Initale Einstellungen
### Alias

Für Debian, systemweite aliase für interaktive Shells.
```
/etc/profile.d/alias.sh
```


### history

https://askubuntu.com/questions/67283/is-it-possible-to-make-writing-to-bash-history-immediate

Try putting this into your .bashrc:
```
shopt -s histappend                      # append to history, don't overwrite it
export PROMPT_COMMAND="history -a; history -c; history -r; $PROMPT_COMMAND"
```

## Bash Programierung

### Tests

https://hangar118.sdf.org/p/bash-scripting-guide/reference_cards.html

#### String Tests


|    | String                 |
|----|------------------------|
| =  | Equal to               |
| == | Equal to               |
| != | Not equal to           |
| \< | Less than (ASCII) *    |
|    |                        |
| \> | Greater than (ASCII) * |
|    |                        |
| -z | String is empty        |
| -n | String is not empty    |

Prüfen ob eine Variable leer ist.
```
[ -z "$host_ip" ]
```

####  Arithmetic Tests 


|     | Arithmetic           |    
|-----|----------------------|   
| -eq | Equal to               |  
|     |                         | 
| -ne | Not equal to             |
| -lt | Less than                |
| -le | Less than or equal to    |
| -gt | Greater than             |
| -ge | Greater than or equal to |


### for
Bash 3.0+ can use this syntax:
```
for i in {1..10} ; do ... ; done
```
which avoids spawning an external program to expand the sequence (such as seq 1 10).
```
for i in $(seq 1 10); do echo $i done
```
