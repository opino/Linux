# tar 

```
c = create     → erstellen
x = extract    → entpacken
t = list       → Inhalt anzeigen
z = gzip       → gzip
j = bzip2      → bzip2
J = xz         → xz
f = file       → Archivdatei angeben
v = verbose    → Details anzeigen
```

##  Dateien mit tar archivieren

```
tar -cf archiv.tar datei1.txt datei2.txt
```

## Mit gzip komprimieren → .tar.gz

```
tar -czf archiv.tar.gz datei1.txt datei2.txt
```

##  ganzen Ordner packen:

```
tar -czf backup.tar.gz /opt/questions
```

##  Archiv entpacken

```
tar -xzf archiv.tar.gz
```

## Inhalt anzeigen, ohne zu entpacken

```
tar -tzf archiv.tar.gz
```
