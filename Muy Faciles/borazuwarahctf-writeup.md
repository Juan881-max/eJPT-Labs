Maquina de Dockerlabs, categoria muy facil, veremos ...

La descargo, ejecuto y hago un nmap:

![Nmap](../Imagenes/borazuwarah/1.png)

Abiertos 22 y 80, voy al navegador:

![Huevo](../Imagenes/borazuwarah/2.png)

Sorpresa!!!

Reviso el codigo fuente, no hay nada.

Busco directorios o archivos con *gobuster*, no encuentro nada.

Descargo la imagen para analizarla con *exiftool*:

![exiftool](../Imagenes/borazuwarah/3.png)

Tengo un usuario, probemos con hydra:

![Hydra](../Imagenes/borazuwarah/4.png)

Tenemos usuario y contraseña:

![ssh](../Imagenes/borazuwarah/6.png)

Estamos dentro, probaremos con sudo -l

![bin-bash](../Imagenes/borazuwarah/7.png)

Pues hay suerte, buso en GTFOBins:

![GFTOBins](../Imagenes/borazuwarah/8.png)

Lo meto directamente:

![root](../Imagenes/borazuwarah/9.png)

Conseguido!!



