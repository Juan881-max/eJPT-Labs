> [!important] Dockerlabs
> La maquina psycho pertenece a Dockerlabs, es sobre la que vamos a trabajar, vamos a intentar vulnerar.
> Desde la pagina de Dockerlabs, la descargamos en Kali, la llevamos al Escritorio, descomprimimos y nos metemos en la carpeta. 
> La corremos con: *sudo bash auto_deploy.sh psycho.tar*
> Empezamos ...

Con nmap vemos las siguientes puertos abiertos:

![Nmap Scan](1.png)

Vamos al navegador por el *puerto 80*, nada que me llame la atencion, excepto en la parte de abajo un mensaje de error. Examino el codigo fuente, no veo nada raro.

Hay que hacer fuzzing, usare *gobuster* en un principio:

![Gobuster](2.png)

Tenemos el directorio */assets/*, veamos que hay:
- Una imagen que no me da ninguna pista.

Sigo con el fuzzing:

![Wfuzz](3.png)

Descubro un archivo oculto, posible LCI, probamos:

![LFI etc Passwd](5.png)

He hallado usuarios:

![Extraccion clave](7.png)

Pruebo a ver si hallo la clave privada de luisillo: Nada
Pruebo a ver si hallo la clave privada de vaxei: Perfecto esta


Y hallamos la 'PRIVATE KEY':
- La copio y le doy permisos, 600 en este caso

![Guardar id_rsa](8.png)

Pruebo a entrar por el puerto 22:

![Permisos clave](9.png)

Estoy dentro, soy vaxei.

Probamos con sudo -l
![Login SSh](10.png)

Busco en la pagina gtfobins:

![Sudo l vaxei](11.png)
Pruebo con el nombre del otro usuario:

![Escalada](12.png)
Funciona soy luisillo

Volvemos al sudo -l
![Sudo l luisillo](13.png)

Veo un archivo paw.py, subo al directorio y lo abro:

![paw py](14.png)

No tengo permisos para editar el archivo, asi que hare Python Library HiJacking:

- veo que se importa subprocess, intentare cambiarlo

![Acceso Root](16.png)

Cuando lo importe, me dara acceso ... 

![Verificacion](45.png)
