Candy es una maquina de Dockerlabs, de la seccion Facil

Descargamos, descomprimimos y corremos la maquina.

![IMG-20260115093622266](../Imagenes/candy/1.png)

Hacemos un nmap, para ver puertos y servicios:

![IMG-20260115093830733](../Imagenes/candy/2.png)
![[IMG-20260115093833539](../Imagenes/candy/3.png)

Puerto 80 abierto, veamoslo en el navegador:

![IMG-20260115094017900](../Imagenes/candy/5.png)

Vemos un Panel de Login, pero no tenemos mas informacion.
Hacemmos fuzzing con gobuster:

![IMG-20260115095008327](../Imagenes/candy/7.png)

![IMG-20260115095018856](../Imagenes/candy/8.png)

Bien por  la salida, vemos que es un CMS, un Joomla, vemos /templates, adminstrator/ ...y /robots.txt, veamos que hay ahi:
![IMG-20260115095435390](../Imagenes/candy/9.png)


admin y contraseña, no funciona directamente, esta en Base64, la decodificamos:

![IMG-20260115095617994](../Imagenes/candy/10.png)

Probamos a entrar logeandonos en administrator:

![IMG-20260115095814507](../Imagenes/candy/12.png)

Estoy dentro, en templates, donde veo que tengo el archivo error.php(que podria editar) o la posibilidad de crear uno nuevo. Voy a crar un archivo .php, que al abrirlo me de de una revshell.

![IMG-20260115100116552](../Imagenes/candy/13.png)
![IMG-20260115101616324](../Imagenes/candy/45.png)



Creamos el archivo con un payload basico y lo guardamos, escuchamos desde el puerto 4444:

![IMG-20260115101122391](../Imagenes/candy/17.png)

Estamos dentro. Lo primero haremos el tratamiento de la TTY, para tener una shell mas estable.

![IMG-20260115101504588](../Imagenes/candy/19.png)
![IMG-20260115101518897](../Imagenes/candy/20.png)

Tenemos conexion estable.
Buscamos archivos que nos puedan dar alguna pista:

![IMG-20260115102758442](../Imagenes/candy/21.png)
![IMG-20260115102805521](../Imagenes/candy/22.png)

Aqui hay algo curioso, lo abro:

![IMG-20260115103011341](../Imagenes/candy/23.png)

Informacion muy interesante.
Con la informacion que tengo, entro en luisillo y veo que con el binario  dd puedo acceder a root

![IMG-20260116002413138](../Imagenes/candy/25.png)

Voy a GTFObins:
Segun GTFObins, dd permite redirigir contenido hacia archivos con permisos de root; asi que puedo sobreescribir /etc/sudoers. 
![IMG-20260116003214540](../Imagenes/candy/27.png)

Probamos:

![IMG-2026011600355011](../Imagenes/candy/29.png)

Soy root
