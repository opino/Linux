# Bash

```
$?    Rückgabe wert des letzten Befehls
```


## Bash Programierung

## Bash Hanbücher

https://tldp.org/LDP/abs/html/refcards.html#AEN22402
https://tldp.org/LDP/abs/html/

https://www-user.tu-chemnitz.de/~hot/unix_linux_werkzeugkasten/bash.html#testexpr
https://www.gnu.org/software/bash/manual/html_node/index.html#SEC_Contents

# history

https://askubuntu.com/questions/67283/is-it-possible-to-make-writing-to-bash-history-immediate

Try putting this into your .bashrc:
```
shopt -s histappend                      # append to history, don't overwrite it
export PROMPT_COMMAND="history -a; history -c; history -r; $PROMPT_COMMAND"
```
