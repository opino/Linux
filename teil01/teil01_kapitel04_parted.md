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
Mit dmesg Kernelmeldungen prüfen ob die Vergrößerung erkannt wurde

##### sdd 1
```
echo 1 > /sys/class/block/sda/device/rescan && growpart /dev/sdd 1 && resize2fs /dev/sdd1
```
##### sdc 1
```
echo 1 > /sys/class/block/sdc/device/rescan && growpart /dev/sdc 1 && resize2fs /dev/sdc1
```
