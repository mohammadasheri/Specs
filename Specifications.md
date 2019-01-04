# Specifications

## DNS SERVER 
```
  sudo subl /etc/dhcp/dhclient.conf
  supersede domain-name-servers 8.8.8.8; # replace the IP with wanted DNS server
  sudo service networking restart
  sudo service network-manager restart
```

## Openconnect VPN
```
ubuntu 16.04 : alias vpn="echo '123' | sudo openconnect 162.223.88.26:8443 -u mohammad --no-cert-check --passwd-on-stdin"
ubuntu 18.04 : alias vpn="echo '123' | sudo openconnect 162.223.88.26:8443 -u mohammad --servercert sha256:f4ecc97157e733a700363363d24dae961a914b752b704b3de02e324ba77b9ce8 --passwd-on-stdin"
```
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
