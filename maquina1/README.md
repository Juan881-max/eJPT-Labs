# Máquina Vulnerable 01: Elevación de Privilegios (Linux)

Esta máquina es un entorno de entrenamiento diseñado para practicar técnicas de **Pentesting** y **Escalada de Privilegios** en sistemas Linux. Ha sido configurada específicamente para simular vectores de ataque comunes en exámenes de certificación como el **eJPT**.

## 🚀 Despliegue del Laboratorio

Puedes desplegar la máquina directamente desde Docker Hub con un solo comando:

```bash
docker run -d --name lab01 -p 80:80 -p 2222:22 juana1234/mis-maquinas-vulnerables:maquina1
```
Objetivos y Aptitudes a Practicar
Reconocimiento Web: Inspección de código fuente y descubrimiento de archivos ocultos.

Explotación de SSH: Uso de credenciales obtenidas para acceso inicial.

Movimiento Lateral: Navegación entre usuarios del sistema aprovechando configuraciones erróneas.

Escalada de Privilegios: Explotación de permisos de sudo mal configurados para obtener acceso de Root.
