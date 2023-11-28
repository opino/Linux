# parted 

## Übersichten, Tabellen und Referenzen 

### Partion & Disks vergrößern

erst Disk vergrößern,
dann Partition vergrößern

```
parted /dev/sdd resizepart 1 '100%'
parted /dev/sdd print
resize2fs /dev/sdd1
```
