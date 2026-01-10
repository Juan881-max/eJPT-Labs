Maquina de Dockerlabs, nivel muy facil.

Descargo la maquina y la despliego.

Hago un nmap 

![nmap](../Imagenes/tproot/1.png)

Puertos 21 y 80 abiertos, voy al navegador.
Nada, la pagina principal de apache.

Busco directorios o archivos ...

![gobuster](../Imagenes/tproot/2.png)

Solo el index.html ...

Pruebo otra cosa, quiza la version de vsftpd 2.3.4 sea vulnerable, pruebo con metasploit

![msfconsole](../Imagenes/tproot/3.png)

Tenemos un exploit, tras ver las opciones solo me pide el RHOSTS, lo meto co corro y tengo una sesion abierta, pero se cierra rapido.

![exploit](../Imagenes/tproot/4.png)

Compruebo el numero de sesion, y vuelvo a meterlo, funciona

![sessions](../Imagenes/tproot/5.png)

Genero un prompt y busco la flag de root

![root](../Imagenes/tproot/7.png)

Hecho, maquina facil!!
