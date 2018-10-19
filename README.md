# KieaVirtualBox
VirtualBox projects

-----
## 우분투 데스크탑 OS 로그인시 루트 관리자로 로그인하는 방법
    1. open terminal
    2. active the root account
        $ sudo passwd root
        
    3. change login
        $ sudo gedit /etc/lightdm/lightdm.conf
            .....
            autologin-user=root
            .....
    4. save and reboot
-----
## References  
> [Install the Latest VirtualBox on Ubuntu 18.04 LTS](https://websiteforstudents.com/install-the-latest-virtualbox-on-ubuntu-18-04-lts/ "Install the Latest VirtualBox on Ubuntu 18.04 LTS")  
> [How To Install VirtualBox on Ubuntu 18.04](https://linuxize.com/post/how-to-install-virtualbox-on-ubuntu-18-04/ "How To Install VirtualBox on Ubuntu 18.04") - install OK!!  
> [How to Mount and Use exFAT Drive on Ubuntu Linux (Quick Tip)](https://www.youtube.com "YouTube Search: 'ubuntu 18.04 mount exfat'")  
...
