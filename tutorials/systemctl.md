# Systemctl

Sirve para gestionar los servicios de la maquina

## Gestión de los servicios
Nota: Todos los comandos de pueden usar sin el **.service**, pero por claridad se mantiene en el tutorial

Inicio del servicio

```
sudo systemctl start application.service
```

Parar el servicio

```
sudo systemctl stop application.service
```

Reiniciar el servicio

```
sudo systemctl restart application.service
```

Recargar el servicio
```
sudo systemctl reload application.service
```

Si no estas seguro si el servicio es capaz de recargar o no, puedes usar el siguiente (si puede recarga, si no, reinicia)
```
sudo systemctl reload-or-restart application.service
```

Activar el servicio para que se inicie al arranque del dispositivo

```
sudo systemctl enable application.service
```

Desactivar el servicio para que no se inicie al arranque del dispositivo

```
sudo systemctl disable application.service
```

Ver el estado  del servicio

```
sudo systemctl status application.service
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

para saber si el servicio esta activo (ejecutando) usa:
```
systemctl is-active application.service
```
devolvera el estado del servicio, normalmente `active` o `inactive`. Tiene exit code 0 si está activo.

Para saber si el servicio esta activado al inicio se usa:
```
systemctl is-enable application.service
```
devolvera el estado del servicio, normalmente `enable` o `disable`. Tiene exit code 0 si está activado al inicio y 1 si no.

También podemos comprobar si ha fallado: 
```
systemctl is-failed application.service
```
devolverá `active` o `failed` si ha ocurrido algo. Si se detiene normalmente, `unknown` o `inactive`. El exit code es 0 si ha fallado algo y 1 en el resto de casos

# Revisión del estado del sistema



# External links

<https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units>

<https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files>


