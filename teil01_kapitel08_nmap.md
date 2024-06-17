
# nmap 

Since Nmap is free, the only barrier to port scanning mastery is knowledge.

## Portrange scannen 

```
nmap -sS -p1000-7000 example.com
```

## Optionen 

https://nmap.org/man/de/man-briefoptions.html

### Port Scanning Techniques

https://nmap.org/book/man-port-scanning-techniques.html

* sS (TCP SYN scan)
* sT (TCP connect scan)
* sU (UDP scans)
* sY (SCTP INIT scan)
* ...
