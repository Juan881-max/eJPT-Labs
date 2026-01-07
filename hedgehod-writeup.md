Maquina de Dockerlabs, de la seccion muy facil.

Descargamos y desplegamos la maquina.

Hago un *nmap* completo, para ver los puestos disponibles:
![Nmap](hedgehod/1.png)

Abiertos *22 y 80*, voy al navegador:
![web](hedgehod/2.png)

Veo la palabra *tails,* ¿sera un usuario?

Voy a hacer *fuzzing con gobuster*, a ver si encuento algo:

![gobuster](hedgehod/3.png)

Nada, unicamente una pagina *index.html*, es es la que ya conozco.

Probare con *hydra*
![hydra](hedgehod/4.png)

Tarda muchisimo, quiza la palabra este al final del Diccionario, le do y la vuelta:
![hydra2](hedgehod/8.png)

Tras mirar el final del archivo veo huecos vacios, los voy a eliminar:
![ssh](hedgehod/9.png)

Vale ahora si corro hydra con el Diccionario al reves y sin huecos:
![sonic](hedgehod/.png)

Password encontrado, voy a entrar por SSH
![sonic](hedgehod/10.png)

Estoy dentro soy tails.
###### Escalada de Privilegios
Pruebo sudo -l
![all](hedgehod/11.png)

Podemos pivotar al usuario *sonic*
![root](hedgehod/12.png)

Ahora vemos que podemos escalar a root sin mas:
![[IMG-20260107193403403.png]]

Somos root!!!
