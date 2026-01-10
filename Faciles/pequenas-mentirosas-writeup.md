Primera maquina de la session Facil de Dockerlabs

Descargo y despliego la maquina.

![IMG-20260110224223708](../Imagenes/pequenas-mentirosas/1.png)

Primero empezare con un escaneo de puertos:

![[IMG-20260110224404185.png]]

Muestra los puertos 22 y 80 abiertos.

Voy al navegador:

![[IMG-20260110224521053.png]]
Encuentro la primera pista, 'a' podria ser un usuario, voy a probar con hydra:

![[IMG-20260110224727214.png]]

Conseguido: password es *secret*

Entro mediante SSH:

![[IMG-20260110225851906.png]]

Estoy dentro y soy el usuario a.

Busco informacion dentro del usuario a.
He encontrado mucha informacion:

![[IMG-20260110230210001.png]]

En el directorio srv a veces puede haber informacion, en este caso, parece que mucha..

Tambien he encontrado otro usuario:

![[IMG-20260110230352833.png]]

Sin duda, con estas pistas se podra resolver la maquina, voy a hacer fuerza bruta con el nuevo usuario, la opcion mas facil, si no funciona comenzare con las archivos de texto:

![[IMG-20260110230646573.png]]

Mucha suerte, tenemos password, probamos por el puerto 22:

![[IMG-20260110230846051.png]]

Bien estamos dentro y el comando sudo -l funciona, tenemos permisos usando el binario python3. 
Voy a la pagina GTFObins a ver que encuentro:

![[IMG-20260110231058026.png]]

Vamos a probar:

![[IMG-20260110231221550.png]]

Funciona, somos root!!!


