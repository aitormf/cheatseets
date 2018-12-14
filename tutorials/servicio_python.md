# Programa de Python como Demonio


## Creacion e instalacion del servicio
1. Lo primero que hay que hacer es crear un fichero indicando el nombre del servicio: **nombre_servicio.service**, por ejemplo con gedit, o con otro editor cualquiera.

```
gedit nombre_servicio.service
```

2. Copiar lo siguiente dentro. Hay que modificar la descripción y el ExecStart con los datos relativos a nuestro programa

```
[Unit]
Description=tu descripcion aqui
After=multi-user.target

[Service]
Type=idle
ExecStart=/usr/bin/python3 ruta_abosluta_de_tu_programa


[Install]
WantedBy=multi-user.target
```

por ejemplo, para un programa llamado **prueba.py** situado en el home de **pepe** el fichero quedaría asi:

```
[Unit]
Description=programa de prueba
After=multi-user.target

[Service]
Type=idle
ExecStart=/usr/bin/python3 /home/pepe/prueba.py


[Install]
WantedBy=multi-user.target
```

3. copiar este fichero al directorio de *systemd* y configurar el servicio para ejecutarse la inicio

```
sudo cp nombre_servicio.service /lib/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable nombre_servicio.service
```

## Gestion del servicio

Inicio del servicio

```
sudo systemctl start nombre_servicio.service
```

Parar el servicio

```
sudo systemctl stop nombre_servicio.service
```

Ver el estado  del servicio

```
sudo systemctl status nombre_servicio.service
```
mostrará una salida parecida a la siguiente:

```
● nginx.service - A high performance web server and a reverse proxy server
   Loaded: loaded (/usr/lib/systemd/system/nginx.service; enabled; vendor preset: disabled)
   Active: active (running) since Tue 2015-01-27 19:41:23 EST; 22h ago
 Main PID: 495 (nginx)
   CGroup: /system.slice/nginx.service
           ├─495 nginx: master process /usr/bin/nginx -g pid /run/nginx.pid; error_log stderr;
           └─496 nginx: worker process
Jan 27 19:41:23 desktop systemd[1]: Starting A high performance web server and a reverse proxy server...
Jan 27 19:41:23 desktop systemd[1]: Started A high performance web server and a reverse proxy server.
```

Para mas información de gestión usa el siguiente [link](systemctl.md)






