***How to create a service***


go to the directory below and create a file for the service eg ciccio.service

```bash
/etc/systemd/system
touch ciccio.service
```

Then fill with the service details (to refined)
```bash
[Unit]
Description=[description for serice]
Wants=network.target
After=syslog.target network-online.target

[Service]
Type=simple
ExecStart=[path to exec -- eg /home/pi/bots/ciccio.sh]
Restart=on-failure
RestartSec=10
KillMode=process

[Install]
WantedBy=multi-user.target
```

once done, restart the service
```bash
sudo systemctl daemon-reload
sudo systemctl enable ciccio
```
