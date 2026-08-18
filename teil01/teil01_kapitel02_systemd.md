# Systemd

## journalctl

Zeigt Logs vom System oder Systemd Services an.

### Befehle
```
journalctl --list-boots

journalctl --disk-usage
journalctl --vacuum-time=3weeks
```
### Konfiguration  

* /etc/systemd/journald.conf

**  Damit die Einstellungen bei einem Update nicht überschrieben werden; extra Datei:
** /etc/systemd/journald.conf.d/01-journal-size.conf

```
[Journal]
SystemMaxUse=200M
SystemMaxFileSize=128M
```


