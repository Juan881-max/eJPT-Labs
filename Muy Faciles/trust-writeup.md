Descargo la maquina de Dockerlabs, muy facil pone, veremos.

Hago un nmap completo

![Nmap](trust/a.png)

Voy al navegador y veo la pagina de inicio de *Apache*.

Hacemos *fuzzing*:
Con *gobuster*  pasandole extensionesde archivos encuentro un archivo llamado secret:


![Gobuster](trust/s.png)

Entro y veo esto:

![Navegador](trust/d.png)

Entiendo que mario puede ser el usuario, usare *hydra*:

![Hydra](trust/l.png)

<font color="#0070c0">Tenemos usuario y contraseña, y el puerto 22 abierto:</font>

![SSh](trust/f.png)

<font color="#c00000">Estamos dentro!!!</font>

Probamos *sudo -l*

![IMG-20260104181035637](trust/g.png)

Tenemos un *binario*, buscamos en *gtfobins*:

![Gtfobins](trust/h.png)

Lo probamos directamente:

![Root](trust/j.png)

<font color="#c00000">Somos root!!!</font>


