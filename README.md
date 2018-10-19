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

-----
## References  
> [Install the Latest VirtualBox on Ubuntu 18.04 LTS](https://websiteforstudents.com/install-the-latest-virtualbox-on-ubuntu-18-04-lts/ "Install the Latest VirtualBox on Ubuntu 18.04 LTS")  
> [How To Install VirtualBox on Ubuntu 18.04](https://linuxize.com/post/how-to-install-virtualbox-on-ubuntu-18-04/ "How To Install VirtualBox on Ubuntu 18.04") - install OK!!  
> [How to Mount and Use exFAT Drive on Ubuntu Linux (Quick Tip)](https://www.youtube.com "YouTube Search: 'ubuntu 18.04 mount exfat'")  
...
