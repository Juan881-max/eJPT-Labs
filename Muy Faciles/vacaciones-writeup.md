Penultima maquina de la seccion Muy Facil de Dockerlans.

Descargo y despliego la maquina.

Hago un nmap, para ver puestos abiertos

![Nmap](../Imagenes/vacaciones/1.png)

Ok, entro en el Navegador, puerto 80.
Y en el codigo de la pagina veo esto:

![80](../Imagenes/vacaciones/2.png)

Tanto juan como camilo pueden ser usuarios.

Pruebo con hidra, con juan no encuentro nada.
![hydra-juan](../Imagenes/vacaciones/3.png)

Pruebo con camilo y encuentro el password

![hydra](../Imagenes/vacaciones/4.png)

Probamos con SSH, me pide contaseña, y estamos dentro de la maquina.

![camilo](../Imagenes/vacaciones/5.png)

Una vez dentro, vamos a intentar escalar privilegios, esto no funciona:

![no-sudo](../Imagenes/vacaciones/6.png)

Pruebo a buscar binarios, pero no encuentro ninguno que pueda usar:

![find-perm](../Imagenes/vacaciones/7.png)

Busco algun archivo que puedad darme informacion:
```bash
find / -name "*.txt" 2>/dev/null
```

Y encuentro algo, lo leo:

![cat](../Imagenes/vacaciones/8.png)

Probamos si es la contraseña de juan:

  ![ssh-juan](../Imagenes/vacaciones/9.png)

Estamos dentro de juan, probamos sudo -l:

![root](../Imagenes/vacaciones/fin.png)

Busco ruby en GFTObins, y pego el comando.

Somos root!!!
