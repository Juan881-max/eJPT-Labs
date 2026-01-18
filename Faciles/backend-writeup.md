Descargo la maquina backend de Dockerlabs, seccion Facil

Hago un nmap para ver puertos abiertos y versiones

![IMG-20260115093622266](../Imagenes/backend/1.png)
![IMG-20260118205306057]

Puerto 22 y 80 abiertos.
Compruebo posibles exploits para las 2 versiones, no hay nada.
Voy al navegador y encuentro este panel de login

![IMG-20260118205438811]

Tras hacer un par de pruebas, obtengo este mensaje:
![IMG-20260118205519844]

Posiblemente vulnerable a <font color="#c00000">SQLi</font>.
Primero interceptare la peticion del login con <font color="#c00000">BurpSuite</font>.
Segundo usare <font color="#c00000">SQLMap</font>, para extraer info de las bases de datos que haya.

![IMG-20260118211110093]

Interceptado por BurpSite, lo paso al archivo captura.txt, para usarlo con <font color="#c00000">SQLMap</font>

![IMG-20260118211230928]
![IMG-20260118211346095]

Bases de datos, parece que <font color="#c00000">users</font> es en la que hay que entrar:

![IMG-20260118211548311]
![IMG-20260118211555579]

Entramos en usuarios:

![IMG-20260118211737180]
![IMG-20260118211744366]

Veamos que hay dentro de username:

![IMG-20260118211926626]
![IMG-20260118211930330]

Tenemos usuarios y contraseñas, vamos a probar con <font color="#c00000">SSH</font>.
Para paco y $paco$123, no funciona
Para pepe y P123pepe3456P

![IMG-20260118212151027]
![IMG-20260118212154446]

Estamos dentro, somos <font color="#c00000">pepe</font>.

**Escalada de Privilegios**

Sudo -l, no funciona
Pero si en cuentro binarios:

![IMG-20260118212350666]

Atencion tenemos ls y grep
Busco en GTFObins, no encuentro nada.
A ver si puedo listar con ls y leer en el archivo root.

![IMG-20260118213832357]

Ahi esta y sabemos que es un hash, intentare con <font color="#c00000">CrakStation</font>:

![IMG-20260118214053781]

Tenemos <font color="#c00000">contraseña</font> probamos:

![IMG-20260118214202246](../Imagenes/backend/99.png)

<font color="#c00000">Conseguido, soy root !!!</font>
