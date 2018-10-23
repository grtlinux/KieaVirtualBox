# KieaVirtualBox
VirtualBox projects

-----
## How to login of root account on Ubuntu
    1. open terminal
    2. active the root account
        $ sudo passwd root
        
    3. change login
        $ sudo gedit /etc/lightdm/lightdm.conf
            .....
            autologin-user=root
            .....
    4. save and reboot

## How to mount and use exFAT drive on Ubuntu Linux

    $ sudo apt install -y exfat-fuse exfat-utils
        .....
    $ sudo fdisk -l
        .....
    $ sudo mount /dev/sdb1 /mnt
        .....
    $ sudo df -k
        .....
    $ sudo mount
        .....
    $ sudo umount /dev/sdb1
    $ sudo umount /mnt
        .....
    $ sudo df -k
        .....

## How to use SD card on Ubuntu 18.04

    steven@steven-Inspiron-910:~$ lsusb
    
        Bus 001 Device 003: ID 064e:a118 Suyin Corp. 
        Bus 001 Device 002: ID 7392:7622 Edimax Technology Co., Ltd 
        Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
        Bus 005 Device 002: ID 045e:0737 Microsoft Corp. Compact Optical Mouse 500
        Bus 005 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
        Bus 004 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
        Bus 003 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
        Bus 002 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
    
    steven@steven-Inspiron-910:~$ sudo parted -ls
    
        [sudo] password for steven: 
        Model: ATA STEC PATA 16GB (scsi)
        Disk /dev/sda: 15.4GB
        Sector size (logical/physical): 512B/512B
        Partition Table: msdos

        Number  Start   End     Size    Type      File system     Flags
         1      1049kB  14.3GB  14.3GB  primary   ext4            boot
         2      14.3GB  15.4GB  1062MB  extended
         5      14.3GB  15.4GB  1062MB  logical   linux-swap(v1)


        Model: SD SU08G (sd/mmc)
        Disk /dev/mmcblk0: 7948MB
        Sector size (logical/physical): 512B/512B
        Partition Table: msdos

        Number  Start   End     Size    Type      File system     Flags
         1      1049kB  6885MB  6884MB  primary                   boot
         2      6886MB  7947MB  1061MB  extended
         5      6886MB  7947MB  1061MB  logical   linux-swap(v1)


    steven@steven-Inspiron-910:~$ sudo lsblk -o MODEL,NAME,FSTYPE,LABEL,MOUNTPOINT,SIZE
    
        MODEL            NAME        FSTYPE LABEL MOUNTPOINT   SIZE
        STEC PATA 16GB   sda                                  14.4G
                         ├─sda1      ext4         /           13.4G
                         ├─sda2                                  1K
                         └─sda5      swap         [SWAP]      1013M
                         mmcblk0                               7.4G
                         ├─mmcblk0p1                           6.4G
                         ├─mmcblk0p2                             1K
                         └─mmcblk0p5 swap                     1012M

    steven@steven-Inspiron-910:~$
    
    * Probably an installation-issue which can be resolved with re-installation?! - this would concern package udisks2
        
        $ sudo apt install --reinstall udisks2



-----
## References  
> [Install the Latest VirtualBox on Ubuntu 18.04 LTS](https://websiteforstudents.com/install-the-latest-virtualbox-on-ubuntu-18-04-lts/ "Install the Latest VirtualBox on Ubuntu 18.04 LTS")  
> [How To Install VirtualBox on Ubuntu 18.04](https://linuxize.com/post/how-to-install-virtualbox-on-ubuntu-18-04/ "How To Install VirtualBox on Ubuntu 18.04") - install OK!!  
> [How to Mount and Use exFAT Drive on Ubuntu Linux (Quick Tip)](https://www.youtube.com "YouTube Search: 'ubuntu 18.04 mount exfat'")  
> [Ubuntu 18.04 Hangul input key setting](http://progtrend.blogspot.com/2018/06/ubuntu-1804-uim.html "Ubuntu 18.04 Hangul input key setting")  
...
