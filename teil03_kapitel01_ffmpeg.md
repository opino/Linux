# ffmpeg

## Konvertieren 

### FLAC2AIFF

## sinnvoll traversieren

ffmpeg müssen Dateien übergeben werden. Das kann man elegant und effizent durchgeführt werden, am wenigsten 
macht man fasch wenn man stumpf mit dem mit dem großen Hammer alle Dateien erschägt. auf alle Datein draufschlagen  
hier ein paar Möglichkeiten den großen Hammer.

### per find

```
find . -exec ffmpeg -i {} {}.mp3 \;
```


### Ordner rekursiv durchlaufen
