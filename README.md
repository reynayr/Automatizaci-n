<p align="center">
  <img src="images/LogoUTNG.png" alt="Creación del entorno virtual" width="400"/>
</p> 
<p align="center">INGENIERÍA EN TECNOLOGÍAS DE LA INFORMACIÓN ÁREA REDES INTELIGENTES Y CIBERSEGURIDAD</p>
<p align="center">Automatización de Infraestructura Digital</p>
<p align="center">Unidad I. Entornos de desarrollo en la automatización de redes. </p>
<p align="center">Docente: Eric Domenzain Morales </p>
<p align="center">Actividad 1. Archivo README </p>
<p align="center">Autor: Reyna Yazmin Ríos Martínez</p>
<p align="center">GIRI5091</p>
<p align="right">Dolores Hidalgo C. I.N., Gto a 11 de junio de 2025</p>
<p align="right">Ciudad Bolillo Hernandez</p>

# Actividad 1. Archivo README 

## Índice
1. [Introducción](#id1)
2. [Instalación de Docker](#id2)

# <a name="id1"> Introducción </a>
La automatización de redes es un pilar fundamental en la gestión de entornos tecnológicos modernos, permitiendo una mayor eficiencia, menor margen de error y mejor administración de recursos. Este reporte detalla el procedimiento de instalación y configuración de las herramientas necesarias para implementar flujos de automatización, incluyendo la preparación de un entorno de desarrollo funcional.
En particular, se abordan las herramientas **Docker Engine**, **Docker Compose** y **Docker Swagger**, ampliamente utilizadas para la creación y orquestación de contenedores, junto con el uso de **Visual Studio Code** como editor de código y otros complementos esenciales.  
El reporte incluye la descripción de cada herramienta, la instalación técnica paso a paso de las dependencias y entornos necesarios (como Git y plugins de VS Code), así como la ejecución de pruebas de verificación para asegurar el correcto funcionamiento de cada componente.  
Además, se muestran evidencias gráficas que sustentan la realización de cada paso y los resultados obtenidos, garantizando la transparencia del proceso.  
Finalmente, se expone una conclusión que recopila los hallazgos más importantes y se presenta una bibliografía en estilo APA7, la cual recopila los recursos de la comunidad de colaboración y referencias académicas consultadas.  
Este reporte busca demostrar la comprensión y dominio del procedimiento, así como dejar un registro claro y ordenado para futuras implementaciones o consultas.

# Docker 

##  <a name="id2"> Instalación de Docker </a>
INSTALACIÓN
Ir a https://docs.docker.com/engine/install/ubuntu/ y seguir las instrucciones.

Linux mint:
https://www.linuxtechi.com/how-to-install-docker-on-linux-mint/

## Comandos Básicos
Lista de comandos basicos de docker

- **Listar las imagenes disponibles en el sistema**
 ``` shell
 docker ps -a
```

- **Inicializar un contenedor:** 
 ``` shell
docker start [nombre o ID]
```

- **Ver los Logs de los contenedores:** 
 ``` shell
docker logs [nombre contenedor]
```

- **Detener los contenedores:** 
 ``` shell
docker stop [nombre contenedor]
```

- **Eliminar un contenedor:** 
``` shell
docker rm [nombre o ID]
```

- **Eliminar una imagen:** 
``` shell
docker image rm [nombre o ID]
```

# Repositorio de Docker
[Repositorio](https://hub.docker.com/)

# Crear imagen a partir de un archivo Dockerfile
``` shell
docker buil -t nameapp:tag --no-cache --build-arg JAR_FILE=target/*.jar .
```

# Levantar un contenedor a partir de una imagen
``` shell
docker run -p 80:80 -p 8080:8080 --name containername
```

Imagenes
<img src="images/1.png"/>

<img width="50%" src="images/1.png"/>