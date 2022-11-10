Настройка [проксирования](прокси-сервер) в [[Nginx]] 

В [[VigFace]] я делал проксирование с одного Nginx сервера на другой таким конфигом
```nginx
location /checkin {
     include proxy_params;
     proxy_pass http://192.168.48.73/checkin;
     proxy_redirect off;                                                                                                          
     client_max_body_size 10m;
     }                                                                                                                                                                                                                    location /static{                                                                                                               
    proxy_pass http://192.168.48.73/static;                                                                                 }                                       
```

1. `include proxy_params` - это переиспользование стадратной части конфига проксирования [[proxy_params]]

2. `proxy_pass` - это то, куда идет проксирование
3. 