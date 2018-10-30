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


## Oracle VirtualBox 비디오 녹화

	[ Oracle VM VirtualBox 관리자 ]
	VM 선택 > 설정 > 디스플레이 > 비디오 캡쳐 > [v] 비디오 캡쳐 사용하기
		파일경로: /home/kiea/VB/VB/VB_win7_64_H/VB_win7_64_H.webm
		프레임 크기: 1600 x 1200(4:3)
		프레임 레이트: 25 fps
		품질: 1250 kbps
			동영상 5분당 약 45 MB
		확장기능: [ ] Record Audio
		화면: [v] 화면1
	
	[ VM ]
	보기 > 비디오 캡쳐


## System Monitoring on Ubuntu 18.04 Linux with Conky
	$ sudo apt install conky-all
	

## 임시

-----
## References  
> [Install the Latest VirtualBox on Ubuntu 18.04 LTS](https://websiteforstudents.com/install-the-latest-virtualbox-on-ubuntu-18-04-lts/ "Install the Latest VirtualBox on Ubuntu 18.04 LTS")  
> [How To Install VirtualBox on Ubuntu 18.04](https://linuxize.com/post/how-to-install-virtualbox-on-ubuntu-18-04/ "How To Install VirtualBox on Ubuntu 18.04") - install OK!!  
> [How to Mount and Use exFAT Drive on Ubuntu Linux (Quick Tip)](https://www.youtube.com "YouTube Search: 'ubuntu 18.04 mount exfat'")  
> [Ubuntu 18.04 Hangul input key setting](http://progtrend.blogspot.com/2018/06/ubuntu-1804-uim.html "Ubuntu 18.04 Hangul input key setting")  
> [원격로그인(SSH) 접속](https://github.com/jeonghwan-kim/ssh-settings "원격로그인(SSH) 접속")  
> [리눅스 동양상 녹화 Kazam](http://lucy123.tistory.com/entry/%EB%A6%AC%EB%88%85%EC%8A%A4-%EC%B6%94%EC%B2%9C-%EB%8F%99%EC%98%81%EC%83%81-%EB%85%B9%ED%99%94-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-Kazam "Kazam")  
> [System Monitoring on Ubuntu 18.04 Linux with Conky](https://linuxconfig.org/system-monitoring-on-ubuntu-18-04-linux-with-conky "System Monitoring on Ubuntu 18.04 Linux with Conky")  
...
