> [!important] Dockerlabs
> La maquina psycho pertenece a Dockerlabs, es sobre la que vamos a trabajar, vamos a intentar vulnerar.
> Desde la pagina de Dockerlabs, la descargamos en Kali, la llevamos al Escritorio, descomprimimos y nos metemos en la carpeta. 
> La corremos con: *sudo bash auto_deploy.sh psycho.tar*
> Empezamos ...

Con nmap vemos las siguientes puertos abiertos:

![[IMG-20260104153637008.png]]

Vamos al navegador por el *puerto 80*, nada que me llame la atencion, excepto en la parte de abajo un mensaje de error. Examino el codigo fuente, no veo nada raro.

Hay que hacer fuzzing, usare *gobuster* en un principio:

![[IMG-20260104154011616.png]]

Tenemos el directorio */assets/*, veamos que hay:
- Una imagen que no me da ninguna pista.

Sigo con el fuzzing:

![[IMG-20260104155940116.png]]

Descubro un archivo oculto, posible LCI, probamos:

![[IMG-20260104161208441.png]]

He hallado usuarios:

![[IMG-20260104161448645.png]]

Pruebo a ver si hallo la clave privada de luisillo: Nada
Pruebo a ver si hallo la clave privada de vaxei: Perfecto esta


Y hallamos la 'PRIVATE KEY':
- La copio y le doy permisos, 600 en este caso

![[IMG-20260104161900413.png]]

Pruebo a entrar por el puerto 22:

![[IMG-20260104162046672.png]]

Estoy dentro, soy vaxei.

Probamos con sudo -l
![[IMG-20260104162320013.png]]

Busco en la pagina gtfobins:

![[IMG-20260104162414448.png]]
Pruebo con el nombre del otro usuario:

![[IMG-20260104162534944.png]]
Funciona soy luisillo

Volvemos al sudo -l
![[IMG-20260104162630554.png]]

Veo un archivo paw.py, subo al directorio y lo abro:

![[IMG-20260104162820831.png]]

No tengo permisos para editar el archivo, asi que hare Python Library HiJacking:

- veo que se importa subprocess, intentare cambiarlo

![[IMG-20260104163828261.png]]
Cuando lo importe, me dara acceso ... 

![[IMG-20260104164655227.png]]
