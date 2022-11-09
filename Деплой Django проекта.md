Деплой [[Django]] проекта с [[Nginx]] и [[Gunicorn]]

1.  [[Установка всех компонентов]]
2. Как только мы установили компоненты нужно добавить в автозагрузку [[Nginx]]
```bash
systemctl start nginx
systemctls enable nginx
```
3. Обновляем [[Pip]]
```bash 
pip3 install --upgrade pip
```
4. Устанавливаем [[Virtualenv]]
5. Создаем папку проекта 
```bash
mkdir <Название папки проекта>
```
6. Создаем виртуальное окружение в папке проекта
```bash
virtualenv <Название виртуального окружения>
```

_Крч дальше будет костыль, у меня почему-то проблемка, когда я делаю с виртуальным окружением, пришлось установить и в виртуальное все Pip-пакеты и в общее, чтоб все заработало_

7. Заходим в виртуальное окружение
```bash
source <Название вирутального окружения>/bin/activate
```
8. Скачиваем нужные либы питона (вот тут я устанавливал и в виртуальное окружение и в общее)
```bash
pip install django gunicorn и т.д
```
10. Скачиваем [[Git]] и клонируем проект
```bash
sudo apt install git
git clone <Ссылка на скачивание>
```

Проверяем сначала в Django
```bash 
python3 ./manage.py runserver 0.0.0.0:5000
```
Потом через [[Gunicorn]] 
```bash
gunicorn --bind 0.0.0.0:5000 <Название главного модуля>.wsgi
```

### Конфигурируем файлы

1. Первым делом редактируем файл [[gunicorn.socket]] `/etc/systemd/system/gunicorn.socket`
```Gunicorn
[Unit]
Description=gunicorn socket
[Socket]ListenStream=/run/gunicorn.sock
[Install]
WantedBy=sockets.target
```

2. Редактируем файл [[gunicorn.service]] `/etc/systemd/system/gunicorn.service`
```Gunicron
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
3. Нужно дать разрешение на папку с проектом иначе будет `permission denided`
```bash
chmod 777 ./<Директория Джанго проекта>
```
4. Перезагружаем [[systemd]] [демон](Демон) комнадой
``` bash 
systemctl daemon-reload
```
5. 




