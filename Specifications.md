# Specifications

## DNS SERVER 
```
  sudo subl /etc/dhcp/dhclient.conf
  supersede domain-name-servers 8.8.8.8;
  sudo service networking restart
  sudo service network-manager restart
```

## Openconnect VPN
```
ubuntu 16.04 : alias vpn="echo '123' | sudo openconnect 162.223.88.26:8443 -u mohammad --no-cert-check --passwd-on-stdin"
ubuntu 18.04 : alias vpn="echo '123' | sudo openconnect 162.223.88.26:8443 -u mohammad --servercert sha256:f4ecc97157e733a700363363d24dae961a914b752b704b3de02e324ba77b9ce8 --passwd-on-stdin"
```
note: remove sudo if want to use it for specific user.

If you want to crate a shortcut icon for this you can use this command:
```
sudo nano /usr/share/applications/Vpn.desktop
```
This will open an editor and paste it there:
```
[Desktop Entry]
Name=Vpn
Exec=bash -c 'exec bash -i <<<"vpn"'
Icon=/home/mohammad/Pictures/icon.png
Terminal=true
Type=Application
Categories=Utility;Application;
```
Change <b>Icon</b> with your favoried icon.
## format bootabled disk on windows os
```
1- Hit Windows Key, type cmd and hit Ctrl+Shift+Enter. This will force it to open as admin.
2- Run diskpart
3- Run :list disk
4- Run :select disk 2 (based on my system)
5- Run :clean
6- Run :create partition primary
7- Run :select partition 1 (based on my system)
8- Run :format fs=ntfs quick
9- Run :active
10- Run :exit
* Reference : https://davidzych.com/install-windows-10-from-a-usb-flash-drive/
```
## install python 3.6
```
sudo apt build-dep python3.5
cd /tmp
wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tar.xz
sudo tar -xvf Python-3.6.*.tar.xz
cd Python-3.6.*
sudo ./configure
sudo make -j4
sudo make altinstall
```
## Remove Mysql
```
sudo dpkg -r mysql-client-5.7
sudo dpkg -r mysql-server-5.7
sudo dpkg -r libmysqlclient20:i386
sudo dpkg -r libmysqlclient20:amd64
sudo dpkg -r libmysqlclient18:amd64
sudo dpkg -r mysql-common
sudo apt-get purge mysql\* mariadb\* libmysql\* libmariadb\*
sudo apt purge mysql-client-5.7 mysql-client-core-5.7 mysql-common mysql-server-5.7 mysql-server-core-5.7 mysql-server
sudo apt update && sudo apt dist-upgrade && sudo apt autoremove && sudo apt -f install
sudo apt install mysql-server
```

## share file using scp in a network
```
scp /home/mohammad/Downloads/Rick.And.Morty.S01E01.1080p.BDRip.x265.Pseudo.BLAXUP.COM.mkv amir@192.168.1.168:
```
## sahab gmail
```
mindifyapp@gmail.com
ABCabc123!@#
```
## macos setup
``
VBoxManage modifyvm "macos" --cpuidset 00000001 000106e5 00100800 0098e3fd bfebfbff
VBoxManage setextradata "macos" "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct" "iMacSierra1,3"
VBoxManage setextradata "macos" "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0"
VBoxManage setextradata "macos" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Iloveapple"
VBoxManage setextradata "macos" "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"
VBoxManage setextradata "macos" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1
``
## find ssh1 and ssha256 key for android
```
keytool -list -v -keystore /home/mohammad/Downloads/sahabpardazAndroidKey.jks
```
## delete alias from key store for android
```
keytool -delete -alias sendtone -keystore /home/mohammad/Downloads/sahabpardazAndroidKey.jks
```
##sign with google play key
```
keytool -importcert -file upload_cert.der -keystore /home/mohammad/Desktop/sahab/sahabpardazAndroidKey.jks
```

## Resolve conflict of Ubuntu 18 keyshortcuts with Intellij
For example we resolve Ctrl+Alt+L key conflict.
Use this command to find all shortcuts ends with l: 
```
gsettings list-recursively | grep -i \>l\'
```
Then the result is this:
```
org.gnome.settings-daemon.plugins.media-keys screensaver '<Control><Alt>l'
```
Then use this command to set "screensaver" keyshortcut to nothing:
```
gsettings set org.gnome.settings-daemon.plugins.media-keys screensaver []
```

# open port
```
sudo usermod -a -G dialout <user>
sudo usermod -a -G tty <user>
```

# kill spersific process on port
```
sudo kill -9 `sudo lsof -t -i:80`
```

#collate mysql
[mysqld]
#
# * Basic Settings
#
user            = mysql
pid-file        = /var/run/mysqld/mysqld.pid
socket          = /var/run/mysqld/mysqld.sock
port            = 3306
basedir         = /usr
datadir         = /var/lib/mysql
tmpdir          = /tmp
lc_messages_dir = /usr/share/mysql
lc_messages     = en_US
skip-external-locking
#skip-name-resolve
character-set-client-handshake = FALSE
character-set-server = utf8
collation-server = utf8_general_ci
[10:37 PM] bayad zire [mysqld] bashe
