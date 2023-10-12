# Systemd

## journalctl

https://askubuntu.com/questions/1012912/systemd-logs-journalctl-are-too-large-and-slow

### Größenbeschränkungen für die journalctllog 

* dsfgdsfg
  
/etc/systemd/journald.conf.d/01-journal-size.conf

```
[Journal]
SystemMaxUse=200M
SystemMaxFileSize=128M
```


```
journalctl --disk-usage
```
