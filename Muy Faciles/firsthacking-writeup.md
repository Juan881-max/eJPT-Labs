Maquina de Dockerlab, categoria muy facil.

Descargamos y desplegamos la maquina.

Hacemos un nmap completo.

![ftp](firsthacking/1.png)

Unicamente el puerto 21 abierto.

Veamos si con metasploit puedo conseguir algo metiendo la version de la vsftpd:


![msfconsole](firsthacking/3.png)


Bien tenemos un exploit, veamos que nos pide y lo metemos:

![RHOSTS](firsthacking/4.png)

Nos pide la IP de la maquina victima solamente:

![sessions](firsthacking/5.png)

Lo meto, hay una sesion abierta, pero no creada ...

![root](firsthacking/6.png)

Busco y meto en numero de sesion y soy root!!

Para obtener un prompt:

![bin-bash](firsthacking/7.png)






