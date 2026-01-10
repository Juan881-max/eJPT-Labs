Descargo la maquina de Dockerlabs, muy facil pone, veremos.

Hago un nmap completo

![Nmap](../Imagenes/trust/a.png)

Voy al navegador y veo la pagina de inicio de *Apache*.

Hacemos *fuzzing*:
Con *gobuster*  pasandole extensionesde archivos encuentro un archivo llamado secret:


![Gobuster](../Imagenes/trust/s.png)

Entro y veo esto:

![Navegador](../Imagenes/trust/d.png)

Entiendo que mario puede ser el usuario, usare *hydra*:

![Hydra](../Imagenes/trust/l.png)

<font color="#0070c0">Tenemos usuario y contraseña, y el puerto 22 abierto:</font>

![SSh](../Imagenes/trust/f.png)

<font color="#c00000">Estamos dentro!!!</font>

Probamos *sudo -l*

![IMG-20260104181035637](../Imagenes/trust/g.png)

Tenemos un *binario*, buscamos en *gtfobins*:

![Gtfobins](../Imagenes/trust/h.png)

Lo probamos directamente:

![Root](../Imagenes/trust/j.png)

<font color="#c00000">Somos root!!!</font>


