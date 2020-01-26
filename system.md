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
