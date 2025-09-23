#Plex installed directly in the VM

#media folders mapped to /volume1


drwxr-xr-x  2 plex plex    0 Sep 19 16:50 downloads/
drwxr-xr-x  2 plex plex    0 Sep 22 07:25 music/
drwxr-xr-x  2 plex plex    0 Sep 21 08:19 video/

#volume mounts (credentials to the nas saved in a .nas-credentials file)

root@iflex-vm-plex-01:/etc# cat fstab
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a
# device; this may be used with UUID= as a more robust way to name devices
# that works even if disks are added and removed. See fstab(5).
#
# <file system> <mount point>   <type>  <options>       <dump>  <pass>
# / was on /dev/ubuntu-vg/ubuntu-lv during curtin installation
/dev/disk/by-id/dm-uuid-LVM-gStZUSpb0ZIbzBiLpVnFN1q7RwPndimIrhsfc8m51cD4vQmRBIW4OSuJeeymUrp4 / ext4 defaults 0 1
# /boot was on /dev/sda2 during curtin installation
/dev/disk/by-uuid/b95ff1f7-092e-46ff-825b-69c2b6eea9a7 /boot ext4 defaults 0 1
# /boot/efi was on /dev/sda1 during curtin installation
/dev/disk/by-uuid/2C37-8984 /boot/efi vfat defaults 0 1
/swap.img	none	swap	sw	0	0

//10.10.2.85/downloads /volume1/downloads cifs credentials=/root/.nas-credentials,uid=plex,gid=plex,iocharset=utf8,vers=3.0 0 0
//10.10.2.85/music    /volume1/music    cifs credentials=/root/.nas-credentials,uid=plex,gid=plex,iocharset=utf8,vers=3.0 0 0
//10.10.2.85/video    /volume1/video    cifs credentials=/root/.nas-credentials,uid=plex,gid=plex,iocharset=utf8,vers=3.0 0 0