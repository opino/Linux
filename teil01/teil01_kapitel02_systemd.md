# Systemd

## journalctl

Zeigt Logs vom System oder Systemd Services an.

### Befehle
```
journalctl -u nginx
journalctr -b0 -r 

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

## systemctr

Services und Units starten, stoppen und verwalten

### Befehle

```
systemcttr [start|stop|restart|enable|disable|status] nginx

systemctl list-units
```

### systemd-analyze

```
systemd-analyze critical-chain nginx.service
```
