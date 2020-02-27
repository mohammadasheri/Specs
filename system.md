# system specification

## create service
create new file name.service in /etc/systemd/system
```
[Unit]
Description=Microblog web application
After=network.target

[Service]
User=mohammad
WorkingDirectory=/home/mohammad/PycharmProjects/blog
ExecStart=/home/mohammad/PycharmProjects/blog/venv/bin/gunicorn -b localhost:5000 -w 4 blog:app
Restart=always

[Install]
WantedBy=multi-user.target
```
## run service
```
systemctl daemon-reload
systemctl start name.service
systemctl stop application.service
```
## list active servers
```
netstat -pnlt
```
## list system media
```
lsblk
```

## copy files with rsync
```
rsync -avzh ubt16@192.168.1.106:/home/ubt16/arsheh_backend /tmp
```
## print directory size
```
du -sh
```
## VM's pre-install 
```
sudo apt install dstat ncdu pigz unzip pv logtop
```

## database
```
alter table app_version CONVERT TO CHARACTER SET utf8
show create table song;
```
## db collate
```
CREATE DATABASE arshehdb CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
