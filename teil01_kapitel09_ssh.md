# SSH

## Schlüsselerstellung 

Welchen Algorithmus sollte verwendet werden?

* sicherstere Algorithmus im Juni 2024 zur Genernierung von SSH-Keys verfügbar ist, ist ED25519
* * https://www.anleitungen.rrze.fau.de/betriebssysteme/linux/sonstige-dokumentation/empfehlungen-fuer-ssh-keys/
* RSA mit geringer Schlüssellänge oder DSA gilt als unsicher

```
ssh-keygen -o -a 100 -t ed25519
```

## Schlüssel kopieren

```
ssh-copy-id -p 23 -i ~/.ssh/id_rsa.pub user@example.com
```

