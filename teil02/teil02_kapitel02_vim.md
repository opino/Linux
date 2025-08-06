# Vim  

## Sonderzeichen anzeigen

https://stackoverflow.com/questions/1675688/make-vim-show-all-white-spaces-as-a-character

```
:set listchars=eol:$,tab:>-,trail:~,extends:>,precedes:<
```


## Vim als Standarteditor unter Ubuntu einrichten



```
update-alternatives --query editor
```

## suchen und ersetzen 

```
:%s/ALTER_TEXT/NEUER_TEXT/g
```


|Bewegen & löschen ||
|---------|------------------|
| d0 |	Vom Cursor bis zum Zeilenanfang alle Zeichen löschen |
| d$ |	Vom Cursor bis zum Zeilenende alle Zeichen löschen |

