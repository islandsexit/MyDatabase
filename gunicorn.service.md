Путь ````
/etc/systemd/system/gunicorn.service



















#### Пример использования:
1. Когда разворачивал [[Django]] на [[Nginx]] с [[Gunicorn]]
`/etc/systemd/system/gunicorn.service`
```gunicorn.service
[Unit]
Description=gunicorn daemon
Requires=gunicorn.socket
After=network.target

[Service]
User=vig (Пользователь)
WorkingDirectory=/home/vig/django/IsFaceCV/face/ (директория с главным модулем)
ExecStart=/home/vig/django/env/bin/gunicorn \ (ссылка на gunicorn в виртОкружении)
          --access-logfile - \
          --workers 1 \
          --bind unix:/run/gunicorn.sock \
          face.wsgi:application

[Install]
WantedBy=multi-user.target
```