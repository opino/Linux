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

```
echo 1 > /sys/class/block/sda/device/rescan
dmesg
growpart /dev/sdd 1
resize2fs /dev/sdd1
```
#### sdc 1
```
echo 1 > /sys/class/block/sdc/device/rescan && growpart /dev/sdc 1 && resize2fs /dev/sdc1
```
