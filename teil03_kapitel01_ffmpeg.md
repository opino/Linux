# ffmpeg

## Konvertieren 

### FLAC2AIFF

## sinnvoll traversieren

Damit Ffmpeg konvertieren kann müssen Dateien übergeben werden. 
Das kann man elegant und effizent durchgeführt werden, der Computer ist aber am besten ausgelastet 
wenn man den großen Hammer schwingt. 

### per find

```
find . -exec ffmpeg -i {} {}.mp3 \;
```


### Ordner rekursiv durchlaufen
