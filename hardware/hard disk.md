### To  list block devices
```
lsblk
```

###  Extend LVM partition and disk

* Check the disk size

```
df -h
```

* If the disk is not increased / not able to see the volume added, then try the below command to display all disks and partitions:

```
sudo lsblk
```

& 

```
sudo fdisk -l
```
The above commads will display the missing disk

### <u>Steps to Extend</u>

* Extend `sda 3` partition to use all available space
* Extend the PV (Physical Volume) where the LVM disk is located
* Extend LV Disk
* Extend filesystem in LV to make disk space available

<u>Extend `sda 3` partition to use all available space</u>
```
sudo growpart /dev/sda 3
```
If we look at the partitions with the sudo lsblk command, we can see that the sda3 partition has been increased 

<u>Extend the PV (Physical Volume) where the LVM disk is located</u>

```
sudo pvresize /dev/sda3
```
<u>Extend LV Disk</u>
```
sudo lvextend -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv
```

<u>Extend filesystem in LV to make disk space available</u>
```
sudo resize2fs /dev/mapper/ubuntu--vg-ubuntu--lv
```

Now check the volume with `df -h ` or `lsblk`