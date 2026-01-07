Maquina de Dockerlabs, de la seccion muy facil.

Descargamos y desplegamos la maquina.

Hago un *nmap* completo, para ver los puestos disponibles:
![[IMG-20260107192122855.png]]

Abiertos *22 y 80*, voy al navegador:
![[IMG-20260107192216427.png]]Veo la palabra *tails,* ¿sera un usuario?

Voy a hacer *fuzzing con gobuster*, a ver si encuento algo:
![[IMG-20260107192353078.png]]

Nada, unicamente una pagina *index.html*, es es la que ya conozco.

Probare con *hydra*
![[IMG-20260107192544468.png]]

Tarda muchisimo, quiza la palabra este al final del Diccionario, le do y la vuelta:
![[IMG-20260107192705623.png]]

Tras mirar el final del archivo veo huecos vacios, los voy a eliminar:
![[IMG-20260107192806789.png]]

Vale ahora si corro hydra con el Diccionario al reves y sin huecos:
![[IMG-20260107192902371.png]]

Password encontrado, voy a entrar por SSH
![[IMG-20260107193010693.png]]

Estoy dentro soy tails.
###### Escalada de Privilegios
Pruebo sudo -l
![[IMG-20260107193205781.png]]

Podemos pivotar al usuario *sonic*
![[IMG-20260107193303110.png]]

Ahora vemos que podemos escalar a root sin mas:
![[IMG-20260107193403403.png]]

Somos root!!!
