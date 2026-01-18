Maquina de Dockerlabs, de la seccion Facil.
Descargo la maquina, la descomprimo y la activo.

Hago un ping para ver si tengo conexion:

![IMG-20260118013644453]

Hago un Nmap completo para ver puertos abiertos y servicios:

![IMG-20260118013644628]
![IMG-20260118013644741]

Bien, veo que tengo abiertos los puertos 22 y 8080(algo extraño este 8080).
Voy al navegador, nada.

Hago fuzzing web con gobuster sobre http://172.17.0.2:8080:

![IMG-20260118013644844]
![IMG-20260118013644928]

Tenemos varios directorios y archivos, voy a ver login:

![IMG-20260118013645011]

Tenemos un panel de login pero no tenemos ni usuario, ni contraseña, pruebo los mas comunes, pero no funcionan.
Vuelvo a los puertos abiertos, aver si encuentro alguna pista, busco posibles exploits en las versiones que tengo de SSH, hago whatweb ...

![IMG-20260118013645089]

Busco exploits en esta version de jenkins:

![IMG-20260118013645177]

Bien, tenemos exploit. 
Veo que puede leer archivos.
Lo busco en la web y lo descargo como exploit1.py

![IMG-20260118013737046]

Le doy permisos, y lo ejecuto poniendo usuario y ruta:

![IMG-20260118013948844]
![IMG-20260118014017305]

Funciona tengo usuarios, probare con hydra si saco la contraseña:

![IMG-20260118014138685]
![IMG-20260118014252502]

Estamos, entramos con SSH:

![IMG-20260118014311533]

Somos bobby, probamos sudo -l:

![IMG-20260118105546583]

Tendremos acceso al usuario pinguinito, mediante el binario python3. Busco en GTFObins:

![IMG-20260118105710030]

Soy el usuario pinguinito, sudo -l

![IMG-20260118105800137]

Tenemos un script.py veamos lo que hay dentro y que podemos hacer:

![IMG-20260118105932290]

Es un simple archivo, que copia un archivo y lo envia a otro destino.
Tengo permisos de ejecucion y de lectura, pero no de escritura.
Puedo crear un archivo con el mismo nombre en el mismo lugar, y borrar el que hay.

![IMG-20260118110809589]

Aqui tenemos el script, le doy permiso de ejecucion y lo lanzo:

![IMG-20260118110902367](../Imagenes/secretjenkins/26.png)

Conseguido, soy root!!
