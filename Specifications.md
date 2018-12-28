# DNS SERVER 
```
  sudo subl /etc/dhcp/dhclient.conf
  supersede domain-name-servers 8.8.8.8; # replace the IP with wanted DNS server
  sudo service networking restart
  sudo service network-manager restart
```

# L2TP Connection
## Install L2TP
```
sudo add-apt-repository ppa:nm-l2tp/network-manager-l2tp  
sudo apt-get update  
sudo apt-get install network-manager-l2tp
sudo apt-get install network-manager-l2tp-gnome
```

##Create VPN
?????
## SSH to stream
```
ssh -Y stream@172.18.131.130
```
## Virtual env
```
source ~/.venv3.5/bin/activate
```