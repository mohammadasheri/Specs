# DNS SERVER 
```
  sudo nano /etc/dhcp/dhclient.conf
  supersede domain-name-servers 8.8.8.8; # replace the IP with wanted DNS server
  sudo service networking restart
  sudo service network-manager restart
```
