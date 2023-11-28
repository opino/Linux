# Bash

Dieses Kapitel sollte in 3 Teile eingeteilt werden

1. Übersichten, Tabellen und Referenzen
1. Inital Einstellungen
1. Shell Programierung


## Übersichten, Tabellen und Referenzen 

### Rückgabewerte

```
$?    Rückgabe wert des letzten Befehls
```
### Bash Handbücher

1. https://tldp.org/LDP/abs/html/refcards.html#AEN22402
1. https://tldp.org/LDP/abs/html/
1. https://www-user.tu-chemnitz.de/~hot/unix_linux_werkzeugkasten/bash.html#testexpr
1. https://www.gnu.org/software/bash/manual/html_node/index.html#SEC_Contents





## Bash Programierung


# history

https://askubuntu.com/questions/67283/is-it-possible-to-make-writing-to-bash-history-immediate

Try putting this into your .bashrc:
```
shopt -s histappend                      # append to history, don't overwrite it
export PROMPT_COMMAND="history -a; history -c; history -r; $PROMPT_COMMAND"
```
