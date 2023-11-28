### cronjobs

## crontab

#Crontab fuer alle Benutzer auflisten:
```
for user in $(cut -f1 -d: /etc/passwd); do crontab -u $user -l; done
```
