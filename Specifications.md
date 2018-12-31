# Specifications

## DNS SERVER 
```
  sudo subl /etc/dhcp/dhclient.conf
  supersede domain-name-servers 8.8.8.8; # replace the IP with wanted DNS server
  sudo service networking restart
  sudo service network-manager restart
```

## L2TP Connection
## Install L2TP
```
sudo add-apt-repository ppa:nm-l2tp/network-manager-l2tp  
sudo apt-get update  
sudo apt-get install network-manager-l2tp
sudo apt-get install network-manager-l2tp-gnome
```

##Create VPN
?????
## Virtual env
```
source ~/.venv3.5/bin/activate
```
## Openconnect VPN
```
ubuntu 16.04 : alias vpn="echo '123' | sudo openconnect 162.223.88.26:8443 -u mohammad --no-cert-check --passwd-on-stdin"
ubuntu 18.04 : alias vpn="echo '123' | sudo openconnect 162.223.88.26:8443 -u mohammad --servercert sha256:f4ecc97157e733a700363363d24dae961a914b752b704b3de02e324ba77b9ce8 --passwd-on-stdin"
```
