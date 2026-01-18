Maquina de Dockerlabs, de la seccion Facil.
Descargo la maquina, la descomprimo y la activo.

Hago un ping para ver si tengo conexion:

![IMG-20260118013644453](../Imagenes/secretjenkins/1.png)

Hago un Nmap completo para ver puertos abiertos y servicios:

![IMG-20260118013644628](../Imagenes/secretjenkins/2.png)
![IMG-20260118013644741](../Imagenes/secretjenkins/3.png)

Bien, veo que tengo abiertos los puertos 22 y 8080(algo extraño este 8080).
Voy al navegador, nada.

Hago fuzzing web con gobuster sobre http://172.17.0.2:8080:

![IMG-20260118013644844](../Imagenes/secretjenkins/4.png)
![IMG-20260118013644928](../Imagenes/secretjenkins/5.png)

Tenemos varios directorios y archivos, voy a ver login:

![IMG-20260118013645011](../Imagenes/secretjenkins/6.png)

Tenemos un panel de login pero no tenemos ni usuario, ni contraseña, pruebo los mas comunes, pero no funcionan.
Vuelvo a los puertos abiertos, aver si encuentro alguna pista, busco posibles exploits en las versiones que tengo de SSH, hago whatweb ...

![IMG-20260118013645089](../Imagenes/secretjenkins/7.png)

Busco exploits en esta version de jenkins:

![IMG-20260118013645177](../Imagenes/secretjenkins/8.png)

Bien, tenemos exploit. 
Veo que puede leer archivos.
Lo busco en la web y lo descargo como exploit1.py

![IMG-20260118013737046](../Imagenes/secretjenkins/9.png)

Le doy permisos, y lo ejecuto poniendo usuario y ruta:

![IMG-20260118013948844](../Imagenes/secretjenkins/10.png)
![IMG-20260118014017305](../Imagenes/secretjenkins/11.png)

Funciona tengo usuarios, probare con hydra si saco la contraseña:

![IMG-20260118014138685](../Imagenes/secretjenkins/12.png)
![IMG-20260118014252502](../Imagenes/secretjenkins/13.png)

Estamos, entramos con SSH:

![IMG-20260118014311533](../Imagenes/secretjenkins/14.png)

Somos bobby, probamos sudo -l:

![IMG-20260118105546583](../Imagenes/secretjenkins/16.png)

Tendremos acceso al usuario pinguinito, mediante el binario python3. Busco en GTFObins:

![IMG-20260118105710030](../Imagenes/secretjenkins/17.png)

Soy el usuario pinguinito, sudo -l

![IMG-20260118105800137](../Imagenes/secretjenkins/18.png)

Tenemos un script.py veamos lo que hay dentro y que podemos hacer:

![IMG-20260118105932290](../Imagenes/secretjenkins/19.png)

Es un simple archivo, que copia un archivo y lo envia a otro destino.
Tengo permisos de ejecucion y de lectura, pero no de escritura.
Puedo crear un archivo con el mismo nombre en el mismo lugar, y borrar el que hay.

![IMG-20260118110809589](../Imagenes/secretjenkins/22.png)

Aqui tenemos el script, le doy permiso de ejecucion y lo lanzo:

![IMG-20260118110902367](../Imagenes/secretjenkins/26.png)

Conseguido, soy root!!
