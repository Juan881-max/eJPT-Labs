Descargo la maquina de Dockerlabs, muy facil pone, veremos.

Hago un nmap completo

![[IMG-20260104174736608.png]]

Voy al navegador y veo la pagina de inicio de *Apache*.

Hacemos *fuzzing*:
Con *gobuster*  pasandole extensionesde archivos encuentro un archivo llamado secret:


![[IMG-20260104180024541.png]]

Entro y veo esto:
![[IMG-20260104180218178.png]]

Entiendo que mario puede ser el usuario, usare *hydra*:

![[IMG-20260104180405058.png]]

<font color="#0070c0">Tenemos usuario y contraseña, y el puerto 22 abierto:</font>

![[IMG-20260104180725335.png]]

<font color="#c00000">Estamos dentro!!!</font>

Probamos *sudo -l*

![[IMG-20260104181035637.png]]

Tenemos un *binario*, buscamos en *gtfobins*:

![[IMG-20260104181134982.png]]

Lo probamos directamente:

![[IMG-20260104181222882.png]]

<font color="#c00000">Somos root!!!</font>


