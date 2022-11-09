Находится в `/etc/systemd/system/gunicorn.socket`






















#### Пример использования:
1. Когда разворачивал [[Django]] на [[Nginx]] с [[Gunicorn]]
`/etc/systemd/system/gunicorn.socket`
```Gunicorn 
[Unit]
Description=gunicorn socket

[Socket]
ListenStream=/run/gunicorn.sock

[Install]
WantedBy=sockets.target
```