Nueva maquina nivel muy facil de Dockerlabs.

La descargo y la despliego.

Hago un nmap y descubro el puerto 22 abierto, nada mas

![nmap](../Imagenes/breakmyssh/1.png)

Es posible, que el usuario pueda ser <font color="#c00000">root</font>, asi que pruebo con hydra:

![hydra](../Imagenes/breakmyssh/2.png)

Puede pasar que al intentar entrar mediante SSH nos salga esto:

![falla](../Imagenes/breakmyssh/4.png)

Al conectarnos por SSH Kali guarda su huella digital, si luego eliminamos la maquina y entramos con una nueva con la misma IP las huella ya no coinciden.
Asi que debemos borrar todas las entradas pertenecientes a esa IP:

![keygen](../Imagenes/breakmyssh/6.png)

Ahora si entramos por SSH:

![root](../Imagenes/breakmyssh/3.png)

Logrado, soy root.


