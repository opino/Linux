# Systemd

## journalctl

https://askubuntu.com/questions/1012912/systemd-logs-journalctl-are-too-large-and-slow

### Größenbeschränkungen für die journalctl log 
* Damit die Einstellungen nicht nach dem Update weg sind müssen die einstellungen in eine extra Datei:
  
/etc/systemd/journald.conf.d/01-journal-size.conf

```
[Journal]
SystemMaxUse=200M
SystemMaxFileSize=128M
```


```
journalctl --disk-usage
```
