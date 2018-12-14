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

1. Inicio del servicio

```
sudo systemctl start nombre_servicio.service
```

2. Parar el servicio

```
sudo systemctl stop nombre_servicio.service
```

3. Reiniciar el servicio

```
sudo systemctl restart nombre_servicio.service
```

4. Activar el servicio para que se inicie al arranque del dispositivo

```
sudo systemctl enable nombre_servicio.service
```


