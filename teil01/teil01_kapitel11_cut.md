# cut 

## Übersichten, Tabellen und Referenzen 

-d, --delimiter=DELIM
              use DELIM instead of TAB for field delimiter
-f, --fields=LIST
              select only these fields;  also print any line that
              contains no delimiter character, unless the -s option is
              specified

### 


```
docker image ls | tr -s ' ' | cut -d ' ' -f 3
```
#### 

```




