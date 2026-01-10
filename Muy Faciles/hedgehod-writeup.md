Maquina de Dockerlabs, de la seccion muy facil.

Descargamos y desplegamos la maquina.

Hago un *nmap* completo, para ver los puestos disponibles:

![Nmap](../Imagenes/hedgehod/1.png)

Abiertos *22 y 80*, voy al navegador:

![web](../Imagenes/hedgehod/2.png)

Veo la palabra *tails,* ¿sera un usuario?

Voy a hacer *fuzzing con gobuster*, a ver si encuento algo:

![gobuster](../Imagenes/hedgehod/3.png)

Nada, unicamente una pagina *index.html*, es es la que ya conozco.

Probare con *hydra*

![hydra](../Imagenes/hedgehod/4.png)

Tarda muchisimo, quiza la palabra este al final del Diccionario, le do y la vuelta:

![tac](../Imagenes/hedgehod/6.png)

Tras mirar el final del archivo veo huecos vacios, los voy a eliminar:

![sed](../Imagenes/hedgehod/7.png)

Vale ahora si corro hydra con el Diccionario al reves y sin huecos:

![hydra2](../Imagenes/hedgehod/8.png)

Password encontrado, voy a entrar por SSH

![ssh](../Imagenes/hedgehod/9.png)

Estoy dentro soy tails.
###### Escalada de Privilegios
Pruebo sudo -l

![sonic](../Imagenes/hedgehod/10.png)

Podemos pivotar al usuario *sonic*

![all](../Imagenes/hedgehod/11.png)

Ahora vemos que podemos escalar a root sin mas:

![root](../Imagenes/hedgehod/12.png)

Somos root!!!
