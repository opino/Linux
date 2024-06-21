# SSH

- [SSH](#ssh)
  * [Schlüsselerstellung](#schl-sselerstellung)
  * [Schlüssel kopieren](#schl-ssel-kopieren)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>



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

