# parted 

## Übersichten, Tabellen und Referenzen 

### Partion vergrößern

erst Disk vergrößern,
dann Partition vergrößern

```
parted /dev/sdd resizepart 1 '100%'
parted /dev/sdd print
resize2fs /dev/sdd1
```
#### growpart

Growpart ist Teil von dem "cloud-guest-utils" Paket.
```
sudo apt install cloud-guest-utils
```
Mit dem Befehl dmesg Kernelmeldungen prüfen, ob die Vergrößerung erkannt wurde.


##### sdc 1
```
echo 1 > /sys/class/block/sdc/device/rescan && growpart /dev/sdc 1 && resize2fs /dev/sdc1
```

###### sdd 1
```
echo 1 > /sys/class/block/sdd/device/rescan && growpart /dev/sdd 1 && resize2fs /dev/sdd1
```

###### sde 1
```
echo 1 > /sys/class/block/sde/device/rescan && growpart /dev/sde 1 && resize2fs /dev/sde1
```

### Swap vergößern

###### sdb1 SWAP 
```
free -h
swapoff /dev/sdb1
mkswap /dev/sdb1
swapon /dev/sdb1
free -h
```





#
