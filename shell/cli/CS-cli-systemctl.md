# systemctl

###### __show all services__
```bash
systemctl list-units
```

###### __start, stop, restart, reload, status__
```bash
systemctl start|stop|restart|reload|status <service>
```

###### __enable/disable to start automatically__
```bash
systemctl enable|disable <service>
```

###### __check if service is active, enabled or failed__
```bash
systemctl is-active|is-enabled|is-failed <service>
```

###### __reset failed limit__
```bash
systemctl reset-failed <service>
```

###### __reload systemd configuration__
```bash
systemctl daemon-reload
```
