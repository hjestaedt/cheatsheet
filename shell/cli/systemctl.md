# systemctl

###### __show all services__
`systemctl list-units`

###### __start, stop, restart, reload, status__
`systemctl start|stop|restart|reload|status <service>`

###### __enable/disable to start automatically__
`systemctl enable|disable <service>`

###### __check if service is active, enabled or failed__
`systemctl is-active|is-enabled|is-failed <service>`

###### __reset failed limit__
`systemctl reset-failed <service>`

###### __reload systemd configuration__
`systemctl daemon-reload`
