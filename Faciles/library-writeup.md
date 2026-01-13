Maquina de la seccion Facil de Dockerlabs

Descargo, descomprimo  y corro la maquina.

![IMG-20260113003848293](../Imagenes/library/1.png)

Nmap completo, para ver puertos abiertos y servicios

![IMG-20260113004239379](../Imagenes/library/2.png)
![IMG-20260113004248063](../Imagenes/library/3.png)

Veo el puerto 80 y el 22 abiertos. Voy al navegador y me encuentro esto:

![IMG-20260113004409379](../Imagenes/library/4.png)

Podria ser una contraseña, la pruebo con hydra:

![IMG-20260113004933293](../Imagenes/library/5.png)
![IMG-20260113004941127](../Imagenes/library/6.png)

Tenemos usuario y contraseña, entramos por SSH

![IMG-20260113005125031](../Imagenes/library/8.png)

Estamos dentro, y comprobamos que podemos ejecutar un script con python3.

Me ubico en la carpeta y leo el script:

![IMG-20260113005412431](../Imagenes/library/9.png)

El problema es que no puedo editarlo, pero si puedo borrarlo, porque tengo permiso de ejecucion:

![IMG-20260113005620949](../Imagenes/library/11.png)

Puedo eliminarlo y subir otro en su lugar, con el mismo nombre con el contenido que yo quiera:

![IMG-20260113005922102](../Imagenes/library/12.png)

Y le doy permisos:

![IMG-20260113010036386](../Imagenes/library/13.png)

Ahora ejecuto el archivo, con toda su ruta:

![IMG-20260113010306031](../Imagenes/library/14.png)

<font color="#c00000">Soy root!!!!</font>
