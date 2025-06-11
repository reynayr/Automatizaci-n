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

# Actividad 1. Archivo README 

# Introducción
<p style="text-align: justify;">
  La automatización de redes es un pilar fundamental en la gestión de entornos tecnológicos modernos, permitiendo una mayor eficiencia, menor margen de error y mejor administración de recursos. Este reporte detalla el procedimiento de instalación y configuración de las herramientas necesarias para implementar flujos de automatización, incluyendo la preparación de un entorno de desarrollo funcional.
  En particular, se abordan las herramientas <strong>Docker Engine</strong>, <strong>Docker Compose</strong> y <strong>Docker Swagger</strong>, ampliamente utilizadas para la creación y orquestación de contenedores, junto con el uso de **Visual Studio Code** como editor de código y otros complementos esenciales.  
  El reporte incluye la descripción de cada herramienta, la instalación técnica paso a paso de las dependencias y entornos necesarios (como Git y plugins de VS Code), así como la ejecución de pruebas de verificación para asegurar el correcto funcionamiento de cada componente.  
  Además, se muestran evidencias gráficas que sustentan la realización de cada paso y los resultados obtenidos, garantizando la transparencia del proceso.  
  Finalmente, se expone una conclusión que recopila los hallazgos más importantes y se presenta una bibliografía en estilo APA7, la cual recopila los recursos de la comunidad de colaboración y referencias académicas consultadas.  
  Este reporte busca demostrar la comprensión y dominio del procedimiento, así como dejar un registro claro y ordenado para futuras implementaciones o consultas.
</p>


# Docker 

## Docker Engine
<p style="text-align: justify;">
Docker Engine es una plataforma de contenedores liviana que permite desarrollar, empaquetar y ejecutar aplicaciones en entornos aislados llamados contenedores. Es el componente central del ecosistema Docker.
</p>

## Docker Compose. 
<p style="text-align: justify;">
Docker Compose es una herramienta oficial de Docker que permite definir y ejecutar múltiples contenedores de forma simultánea mediante un archivo de configuración YAML. Es ideal para entornos donde varias aplicaciones o servicios deben correr juntas, como bases de datos, servidores web y backends.
</p>

## Docker Swagger
<p style="text-align: justify;">
Swagger (ahora parte del ecosistema OpenAPI) es una herramienta que permite documentar, diseñar, visualizar y probar APIs RESTful de forma interactiva. Combinado con Docker, puedes levantar rápidamente una interfaz gráfica para visualizar y probar tu API sin necesidad de instalar Swagger localmente.
</p>

## INSTALACIÓN
Ir a https://docs.docker.com/engine/install/ubuntu/ y seguir las instrucciones.

# Instalación técnica de docker.
## Requisistos previos
- Sistema operativo: Ubuntu 20.04 / 22.04 (o similar).
- Privilegios de administrador (sudo).
- Conexión a internet.

1. Eliminar versiones antiguas (opcional, pero recomendado)
 ``` shell
sudo apt remove docker docker-engine docker.io containerd runc
```

2. Actualizar el sistema y paquetes requeridos
 ``` shell
sudo apt update
sudo apt install ca-certificates curl gnupg lsb-release
```

3. Agregar la clave GPG oficial de Docker
 ``` shell
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

4. Agregar el repositorio de Docker
 ``` shell
echo \
  "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

5. Instalar Docker Engine y herramientas asociadas
 ``` shell
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

6. Verificar que Docker funciona correctamente
 ``` shell
sudo docker run hello-world
```
Deberías ver un mensaje como: **"Hello from Docker! This message shows that your installation appears to be working correctly."**

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

## Crear imagen a partir de un archivo Dockerfile
``` shell
docker buil -t nameapp:tag --no-cache --build-arg JAR_FILE=target/*.jar .
```

## Levantar un contenedor a partir de una imagen
``` shell
docker run -p 80:80 -p 8080:8080 --name containername
```

# Instalación técnica de VSCode
## ¿Qué es VSCode?
<p style="text-align: justify;">
Visual Studio Code (VSCode) es un editor de código fuente desarrollado por Microsoft, muy usado para programar y trabajar con tecnologías como Docker, Git, Node.js, Python, etc. Es ligero, extensible y compatible con Linux, Windows y macOS.
</p>

1. **Actualiza los repositorios e instala dependencias:**
``` shell
sudo apt update
```
``` shell
sudo apt install wget gpg apt-transport-https
```

2. **Agrega la clave GPG de Microsoft:**
``` shell
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/
```

3. **Agrega el repositorio de VSCode:**
``` shell
sudo sh -c 'echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
```

4. **Instala VSCode:**
``` shell
sudo apt update
sudo apt install code
```

5. **Verifica instalación:**
``` shell
code --version
```
# Instalación técnica de Git. 
## ¿Qué es Git?
<p style="text-align: justify;">
Git es un sistema de control de versiones distribuido, utilizado para rastrear cambios en archivos de código fuente, coordinar el trabajo en equipo y gestionar versiones de proyectos de software. Es fundamental para trabajar con plataformas como GitHub.
</p>

## Instalación en Ubuntu/Linux

1. **Actualizar los repositorios**
``` shell
sudo apt update
```

2. **Instalar Git**
``` shell
sudo apt install git
```

3. **Verificar instalación**
``` shell
git --version
```
Deberías ver algo como:
``` shell
git version 2.34.1
```

## Instalación en Windows

1. Descargar Git para Windows
    - Ir al sitio oficial: https://git-scm.com/download/win
    - El instalador se descarga automáticamente.
2. Ejecutar el instalador
    - Haz doble clic en el archivo **.exe.**
    - Acepta los valores por defecto, especialmente:
        - Editor predeterminado: VSCode (si está instalado).
        - PATH: selecciona "Git from the command line and also from 3rd-party software".
    - Finaliza la instalación.
3. Verificar instalación
    - Abre PowerShell o CMD:
    ``` shell
    git --version
    ```

# Ejecutar la imagen hello-world en Docker
## Objetivo:
Verificar que Docker Engine está instalado, el daemon está corriendo correctamente y tienes permisos suficientes para usarlo.

1. **Ejecutar el comando**
    - Abre una terminal y escribe:
    ``` shell
    docker run hello-world
    ```

### ¿Qué hace este comando?
  - **docker run:** Instruye a Docker a crear y ejecutar un contenedor.
  - **hello-world:** Es una imagen de prueba mínima oficial que imprime un mensaje simple.

### Si la imagen no está en tu sistema...
Docker descargará automáticamente la imagen **hello-world** desde Docker Hub:
``` shell
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
...
```

## Resultado esperado:
Si Docker está funcionando, verás un mensaje como este:
``` shell
Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

# Conclusión 
<p style="text-align: justify;">

</p>

Imagenes
<img src="images/1.png"/>

<img width="50%" src="images/1.png"/>