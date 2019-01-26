# VIM Cheat Sheet


## Globales

Comando | función
--- | --- 
`:saveas file` | guardar como 
`K` | abre el man de la palabra donde está el cursor



## Movimiento del cursor

Comando | función
--- | --- 
`0` | inicio de linea
`$` | final de linea
`gg` | inicio del documento
`G` | final del documento
`5G` | linea 5

## Insert Mode

Comando | función
--- | --- 
`i` | insertar antes del cursor
`I` | insertar al inicio de la linea
`a` | insertar despues del cursor
`A` | insertar al final de la linea
`o` | insertar linea debajo de la actual
`O` | insertar linea encima de la actual
`Esc` | salir del modo

## Editar

Comando | función
--- | --- 
`r` | reemplaxa un carácter
`J` | une la linea con la siguiente con un espacio
`u` | deshacer
`Ctrl + r` | reahacer
`.` | repite el ultimo comando

## Marcar texto (Modo visual)

Comando | función
--- | --- 
`v` | inicia el modo
`V` | Modo visual marcando lineas enteras
`o` | ir al final del texto marcado
`Esc` | salir del modo

Hay más, mirar el link

## Comandos en el modo visual

Comando | función
--- | --- 
`>` | tabula
`<` | Reduce sangria
`y` | copia lo marcado
`d` | borra lo marcado

## Registro

Comando | función
--- | --- 
`:reg` | muestra el registro
`"xy` | Copia en el registro x
`"xp` | pega el registro x

**Nota:** el registro se guarda aunque cierres la aplicacion
**Nota:** el registro 0 siempre es lo ultimo copiado

## Marcas

Comando | función
--- | --- 
`:marks` | muestra las marcas
`ma` | selecciona la actual posicion para la marca a
`a | va a la marca
y`a | copia el texto de la marca

## Copiar y pegar

Comando | función
--- | --- 
`yy` | copia una linea
`2yy` | copia 2 lineas
`yw` | copia la palabra
`y$` | copia hasta el final del linea
`p` | pega detrás del cursor
`P` | pega delante del cursor
`dd` | corta una linea
`2d` | corta 2 lineas
`dw` | corta la palabra
`d$` | corta hasta el final del linea
`x` | corta un carácter

## Salir

Comando | función
--- | --- 
`:w` | guardar
`:w !sudo tee %` | guardar usando sudo
`:wq` | guardar y salir
`:q` | salir
`:q!` | salir descartando cambios
`:wqa` | salir guardando todas las pestañas

## Buscar y reemplazar

Comando | función
--- | --- 
`/pattern` | busca pattern
`?pattern` | busca pattern hacia atrás
`n` | repite la busqueda en la misma dirección
`N` | repite la busqueda en la dirección opuesta
`:%s/old/new/g` | remplaza old por new en todo el documento






## External links
[https://vim.rtorr.com](https://vim.rtorr.com)