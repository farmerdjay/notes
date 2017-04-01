**Setup timer in systemd**

Useful command:
```
systemctl enable 10PMsuspend.timer
systemctl start 10PMsuspend.timer
systemctl list-timers
systemctl daemon-reload
```

/usr/lib/systemd/system/backup.service
```
[Unit]
Description=Suspend the machine at 10pm

[Service]
Type=simple
ExecStart=/home/username/suspend.sh

[Install]
WantedBy=multi-user.target
```

/usr/lib/systemd/system/backup.timer
```
[Unit]
Description=Suspend the machine at 10pm

[Timer]
OnCalendar=*-*-* 22:00:00
Unit=10PMsuspend.service

[Install]
WantedBy=multi-user.target
```
