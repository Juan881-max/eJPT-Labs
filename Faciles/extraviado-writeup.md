Maquina de Dockerlabs, seccion Facil.

Descargo, y corro la maquina.
Hago un ping para ver si hay conexion

![IMG-20260121194516055](../Imagenes/extraviado/1.png)

Hago un nmap para ver puertos abiertos y versiones, vemos el puerto 80 y el 22 abiertos

![IMG-20260121194531605](../Imagenes/extraviado/2.png)
![IMG-20260121194537666](../Imagenes/extraviado/3.png)

ttl 64 Linux
Compruebo posibles exploits para las versiones, nada.
whatweb no me dice nada interesante.
Voy al navegador, y encuentro esto:

![IMG-20260121194952739](../Imagenes/extraviado/4.png)

Esta en base 64, lo decodifico, parece que tenemos un posible usuario y contraseña

![IMG-20260121195158488](../Imagenes/extraviado/5.png)

Probando con SSH

![IMG-20260121195341762](../Imagenes/extraviado/6.png)


Somos daniela, y parece que hay archivos interesantes.

Dentro del directorio secreto, hay un archivo, y este nos muestrauna posible contraseña para diego, otro usuario, que confirmo entrando en /home


![IMG-20260121195734076](../Imagenes/extraviado/7.png)

Comprobamos que diego y ballenanera son validos

![IMG-20260121195926457](../Imagenes/extraviado/8.png)

Son validos, somos el usario diego.

Pruebo con sudo -l, nada

Pruebo listando binarios, nada

Busco archivos y encuentro esto


![IMG-20260121200227032](../Imagenes/extraviado/9.png)

Busco mas

![IMG-20260121200417796](../Imagenes/extraviado/10.png)
![IMG-20260121200424372](../Imagenes/extraviado/11.png)

Encuentro este archivo, con una especie de adivinanza, solucion: osoazul


Lo pruebo con diego:


![IMG-20260121200705318](../Imagenes/extraviado/13.png)


Somos root !!!


