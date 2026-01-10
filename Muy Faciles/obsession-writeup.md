Descargo la laquina de Dockerlabs, es la ultima de la seccion Muy Facil. La despliego.

Hago un nmap completo:

![Nmap](../Imagenes/obsession/obsession/1.png)

Descubro los puertos abiertos 80, 21 y 22. Voy al navegador, y encuentro esto en el codigo fuente:

![web](../Imagenes/obsession/obsession/2.png)

Veo que el usuario que se repite es *russoski*

Asi que pruebo con hidra:

![hydra](../Imagenes/obsession/obsession/3.png)

Encontrado el password, entro por SSH:

![ssh(../Imagenes/obsession/obsession/4.png)

Me pide el password y dentro, soy russoski:

![user](../Imagenes/obsession/obsession/6.png)

Hago un *sudo -l* y me dice que para escalar a root puedo usar el binario vim.
Busco en GFTObins y copio el comando:

![root](../Imagenes/obsession/obsession/7.png)

Soy root.

