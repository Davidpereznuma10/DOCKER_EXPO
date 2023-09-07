## Introducción a Docker: Contenedores y Virtualización Ligera

------

**Slide 1: Introducción**

- Título: ¿Qué es Docker?

  `Docker es una tecnología que te permite empacar, distribuir y ejecutar aplicaciones de manera consistente en diferentes entornos, como tu computadora personal o servidores en la nube. Lo hace utilizando contenedores, que son como pequeñas cajas virtuales que contienen todo lo que una aplicación necesita para funcionar, incluyendo el código, las bibliotecas y las configuraciones.`

------

**Slide 2: Problemas en el Desarrollo de Software Tradicional**

- `La siguiente tabla presenta una lista de problemas comunes que suelen surgir en el desarrollo de software tradicional. Estos desafíos, como las diferencias de entorno, las dependencias conflictivas y la falta de aislamiento, pueden complicar el proceso de desarrollo y afectar la eficiencia y la calidad del software. `

  | Problemas en el Desarrollo de Software Tradicional           |
  | ------------------------------------------------------------ |
  | **Diferencias de Entorno**: Los desarrolladores trabajan en máquinas locales con configuraciones diversas, lo que lleva a problemas de compatibilidad. |
  | **Dependencias Conflictivas**: La gestión de dependencias de bibliotecas y componentes puede ser complicada y propensa a conflictos. |
  | **Aislamiento Insuficiente**: Las aplicaciones interactúan directamente con el sistema operativo subyacente, lo que resulta en un aislamiento insuficiente y posibles interferencias. |
  | **Dificultades en la Implementación**: Preparar una aplicación para su implementación en servidores de producción suele requerir un esfuerzo adicional y puede dar lugar a errores de implementación. |
  | **Dificultades en la Escalabilidad**: Escalar aplicaciones puede ser complicado y requerir configuración manual y cambios en el código. |
  | **Gestión de Versiones Compleja**: La gestión de versiones de aplicaciones puede ser complicada y propensa a errores. |
  | **Colaboración Limitada**: La colaboración entre desarrolladores en diferentes máquinas puede ser difícil debido a las diferencias en los entornos locales. |
  | **Resolución de Problemas Difícil**: Resolver problemas en un entorno tradicional puede ser complicado debido a la falta de aislamiento y la dificultad para replicar problemas en el entorno de desarrollo. |

  Estos son algunos de los desafíos que Docker y la contenerización en general están diseñados para abordar en el desarrollo de software.|

------

**Slide 3: Ventajas de Docker**

- `Docker desempeña un papel fundamental en el desarrollo de software y en todo el ciclo de vida de una aplicación debido a su capacidad para abordar varios desafíos comunes en el desarrollo y la implementación de software. Aquí hay algunas razones clave que destacan la importancia de Docker en el desarrollo de software:`

  | Problemas en el Desarrollo de Software sin Docker |                     Soluciones de Docker                     |
  | :-----------------------------------------------: | :----------------------------------------------------------: |
  |            **Diferencias de Entorno**             | **Portabilidad**: Docker permite empacar aplicaciones y todas sus dependencias en contenedores, lo que hace que sean altamente portátiles. Esto elimina problemas de "funciona en mi máquina pero no en la tuya" y simplifica la gestión de versiones. |
  |           **Dependencias Conflictivas**           | **Reproducibilidad**: Docker utiliza archivos de definición como los Dockerfiles para describir las configuraciones y dependencias de una aplicación. Esto garantiza que todas las instancias de un contenedor sean idénticas, lo que facilita la replicación de entornos y la gestión de versiones de aplicaciones. |
  |           **Aislamiento Insuficiente**            | **Aislamiento**: Los contenedores de Docker proporcionan un alto nivel de aislamiento entre aplicaciones y entre las aplicaciones y el sistema operativo subyacente. Esto mejora la seguridad y la estabilidad, ya que una aplicación en un contenedor no puede interferir con otras aplicaciones o con el sistema anfitrión. |
  |       **Dificultades en la Implementación**       | **Escalabilidad**: Docker facilita la escalabilidad de aplicaciones al permitir la creación rápida de múltiples instancias de contenedores, lo que simplifica la gestión de cargas de trabajo cambiantes y evita problemas de escalabilidad. |
  |       **Dificultades en la Escalabilidad**        | **Desarrollo Colaborativo**: Docker simplifica la colaboración en equipo al permitir que todos los miembros trabajen en el mismo entorno de contenedor. Esto minimiza los problemas de compatibilidad y facilita la implementación de prácticas de Integración Continua y Entrega Continua (CI/CD). |
  |         **Gestión de Versiones Compleja**         | **Gestión de Dependencias**: Docker permite gestionar de manera eficiente las dependencias de las aplicaciones, lo que simplifica la gestión de versiones y garantiza la consistencia entre entornos. |
  |             **Colaboración Limitada**             | **Facilita la Implementación**: Docker simplifica la implementación de aplicaciones al proporcionar una forma consistente de empaquetar y distribuir software. |
  |        **Resolución de Problemas Difícil**        | **Automatización**: Docker se integra fácilmente en herramientas de automatización y orquestación como Docker Compose, Kubernetes y otras, lo que facilita la administración y escalabilidad de aplicaciones en entornos de producción. |

------

**Slide 4: Conceptos Básicos**

1. **Imagen**: Una imagen es un archivo de solo lectura que sirve como plantilla para crear contenedores. Contiene todo lo necesario para ejecutar una aplicación, incluyendo el código de la aplicación, bibliotecas y configuraciones. Las imágenes son la base para crear contenedores.
2. **Contenedor**: Un contenedor es una unidad ligera y portátil que contiene una aplicación y todas sus dependencias, como bibliotecas y configuraciones. Es como una pequeña cápsula que puede ejecutar una aplicación de manera aislada y consistente en cualquier lugar donde Docker esté instalado.
3. **Dockerfile**: Es un archivo de texto plano que contiene instrucciones para construir una imagen de Docker. En un Dockerfile, se especifica qué sistema operativo se usará, qué dependencias se instalarán y cómo se configurará la aplicación.
4. **Docker Hub**: Docker Hub es un servicio en línea que actúa como un repositorio centralizado de imágenes de Docker. En Docker Hub, los desarrolladores pueden compartir, distribuir y descargar imágenes de contenedores predefinidas. Es una fuente valiosa de imágenes listas para usar en Docker.
5. **Orquestación**: La orquestación en Docker se refiere a la gestión de múltiples contenedores en un entorno de producción. Herramientas como Docker Compose y Kubernetes permiten automatizar la implementación, escalabilidad y administración de contenedores.
6. **CLI (Interfaz de línea de comandos)**: Docker se utiliza principalmente a través de comandos en la línea de comandos. La CLI de Docker ofrece una forma sencilla de crear, ejecutar y administrar contenedores.
7. **Puertos**: Los contenedores pueden exponer puertos para permitir la comunicación con otras aplicaciones o servicios. Por ejemplo, puedes exponer el puerto 80 para una aplicación web.
8. **Volúmenes**: Los volúmenes en Docker son mecanismos para persistir datos más allá del ciclo de vida de un contenedor. Esto es útil para almacenar bases de datos u otros datos que deben sobrevivir a la destrucción de un contenedor.
9. **Redes**: Docker permite crear redes virtuales para conectar contenedores y permitir la comunicación entre ellos. Esto es esencial para aplicaciones que constan de varios contenedores que deben comunicarse.
10. **Reglas de Seguridad**: Docker incluye características de seguridad que permiten controlar el acceso a recursos del sistema y aislar contenedores para evitar problemas de seguridad.

------

**Slide 5: Arquitectura de Docker**

1. **Motor de Docker (Docker Engine)**: Es el "corazón" de Docker. Piensa en él como el encargado de crear y ejecutar los contenedores. Dentro de este motor, hay un "Docker Daemon" que es como el "trabajador" que sigue tus órdenes.

2. **Cliente de Docker (Docker Client)**: Es como tu "control remoto" para Docker. Utilizas comandos desde tu computadora con el cliente de Docker para decirle al "Daemon" qué hacer.

3. **Imágenes de Docker (Docker Images)**: Son como "moldes" para crear contenedores. Contienen todo lo que una aplicación necesita para funcionar. Al crear un contenedor, usas una imagen como base.

4. **Contenedores de Docker (Docker Containers)**: Son como "contenedores virtuales" que ejecutan aplicaciones. Cada contenedor es una instancia de una imagen de Docker. Los contenedores son independientes y aislados, lo que significa que no afectan al sistema en el que se ejecutan.

En resumen, Docker funciona así: utilizas el "Cliente" para dar órdenes al "Motor Docker" que utiliza las "Imágenes" para crear y ejecutar los "Contenedores". Esto hace que las aplicaciones sean portátiles y fáciles de gestionar en diferentes entornos.

------

**Slide 6: Instalación de Docker**

- Instalacion en linux:

  Claro, aquí tienes un paso a paso basado en la información que proporcionaste para instalar Docker en un sistema basado en Ubuntu:

  **Paso 1:** Abre una terminal en tu sistema Ubuntu.

  **Paso 2:** Verifica si Docker está previamente instalado ejecutando el siguiente comando:

  ```bash
  docker --version
  ```

  ![docker](https://cdn.discordapp.com/attachments/1103685416206483486/1149347243665653911/image.png)

  Si obtienes un mensaje de error que indica que "docker" no está instalado, continúa con el siguiente paso.

  **Paso 3:** Ejecuta el siguiente comando para actualizar la lista de paquetes del sistema:

  ```bash
  sudo apt update
  ```

  Este comando asegura que tienes la información más actualizada sobre los paquetes disponibles.

  **Paso 4:** Ahora, ejecuta el siguiente comando para instalar Docker:

  ```bash
  sudo apt install docker.io
  ```

  Cuando se te solicite confirmación, presiona "Y" y luego "Enter" para continuar con la instalación.

  **Paso 5:** Una vez que la instalación esté completa, puedes verificar la versión de Docker para asegurarte de que se haya instalado correctamente:

  ```bash
  docker --version
  ```

  ![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464219977252945/image-20230907092431581.png)

  Deberías ver la versión de Docker que se instaló, lo que indica que Docker ahora está disponible en tu sistema.

------

**Slide 7: Uso de Imágenes**

**Cómo funcionan las imágenes en Docker:**

- Las imágenes en Docker son como recetas completas para crear contenedores. Imagina que una imagen es como una receta de pastel que contiene todos los ingredientes y las instrucciones.

- Una imagen puede incluir el sistema operativo, las bibliotecas, el código de la aplicación y todas las configuraciones necesarias.

  **Ejemplo con "Hello, World" en Docker:**

  1. Supongamos que tenemos una imagen llamada "hello-world" que contiene una receta muy simple para mostrar un mensaje "Hello, World" en la pantalla.

  2. Para crear un contenedor a partir de esta imagen, ejecutamos el siguiente comando en Docker:

  ```bash
  docker run hello-world
  ```

  3. Docker tomará la imagen "hello-world", seguirá las instrucciones de la receta y creará un contenedor que muestra un mensaje de "Hello, World" en la pantalla.

     ![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464220237316196/image-20230907093258472.png)

  Este ejemascdcdplo con "hello-world" es una forma común de comprobar que Docker está configurado y listo para ser utilizado en tu sistema.

**LISTA DE COMANDOS PARA IMAGENES**

1. **Listar todas las imágenes en tu sistema:**

   ```bash
   docker images
   ```

   Este comando mostrará una lista de todas las imágenes que tienes en tu sistema. La lista incluye el nombre de la imagen, la etiqueta, el ID de la imagen, el tamaño y cuándo se creó.

2. **Ver detalles de una imagen específica:**

   Para ver detalles específicos de una imagen, como las capas y las etiquetas, puedes ejecutar:

   ```bash
   docker image inspect nombre-de-la-imagen
   ```

   Reemplaza `nombre-de-la-imagen` con el nombre de la imagen que deseas inspeccionar. Esto mostrará una salida JSON con información detallada sobre la imagen.

3. **Ver el historial de una imagen:**

   El siguiente comando te mostrará el historial de capas de una imagen, lo que te permite ver cómo se construyó:

   ```bash
   docker history nombre-de-la-imagen
   ```

4. **Ver el uso de espacio en disco de las imágenes:**

   Para obtener información sobre el espacio en disco que ocupan las imágenes, puedes usar el siguiente comando:

   ```bash
   docker system df -v
   ```

   Esto mostrará el espacio utilizado por imágenes, contenedores y volúmenes.

5. **Limpiar imágenes no utilizadas:**

   Si deseas eliminar imágenes que no están en uso, puedes ejecutar:

   ```bash
   docker image prune
   ```

   Esto eliminará las imágenes que no están asociadas con ningún contenedor en ejecución.

------

**Slide 8: Creación de Contenedores**

**Paso 1:** Descarga la imagen de Ubuntu desde Docker Hub utilizando el siguiente comando:

```bash
docker pull ubuntu
```

![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464220488958094/image-20230907094007649.png)

**Paso 2:** Una vez que la descarga se complete, puedes crear un contenedor a partir de esta imagen utilizando el siguiente comando:

```bash
docker run --name mi-contenedor-ubuntu -it ubuntu
```

**Paso 3:** El sistema te llevará al interior del contenedor, y verás un indicador de que estás en el shell del contenedor.

![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464220778381432/image-20230907094124167.png)

**Paso 4:** Puedes ejecutar comandos dentro del contenedor Ubuntu como lo harías en una instalación de Ubuntu normal. Por ejemplo, puedes ejecutar:

```bash
ls
```

![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464221017452675/image-20230907094200857.png)

**Paso 5:** Cuando hayas terminado de usar el contenedor, puedes salir del shell del contenedor escribiendo `exit`.

![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464221239738499/image-20230907094233160.png)

------

**Slide 9: Dockerfile y Construcción de Imágenes**

1. Crea un directorio para tu proyecto y colócate en él:

   ```bash
   mkdir mi-proyecto-node
   cd mi-proyecto-node
   ```

2. code Crea un directorio en tu sistema y coloca el Dockerfile en ese directorio. Asegúrate de que el Dockerfile tenga exactamente el contenido que proporcionaste en tu pregunta:

```Dockerfile
FROM node

RUN mkdir -p /usr/src/app
#-p se utiliza para asegurarse de que /usr/src/app se cree incluso si los directorios /usr y /usr/src no existen previamente.

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD [ "npm", "run", "dev" ]
```

3. Ejecuta el siguiente comando para construir una imagen a partir del Dockerfile (asegúrate de estar en el directorio que contiene el Dockerfile):

```bash
docker build -t mi-app-node .
```

- Cuando no inicializamos el proyecto de node antes de montar el contenedor 

![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464221566910474/image-20230907104948114.png)

- si iniciamos el proyecto de node

![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464221822759013/image-20230907110306616.png)

- `-t mi-app-node` le da un nombre a la imagen, en este caso, "mi-app-node".

- El último punto `.` indica que el Dockerfile se encuentra en el directorio actual.

- Podemos revisar la creacion de la imagen con el comando 

  ```bash
  docker image ls
  ```

  ![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464222057627789/image-20230907103049034.png)

5. Una vez que la imagen se haya construido con éxito, puedes ejecutar un contenedor basado en esa imagen usando el siguiente comando:

```bash
docker run -p 3000:3000 mi-app-node
```

- `-p 3000:3000` hace que el puerto 3000 del contenedor se mapee al puerto 3000 de tu sistema anfitrión, permitiéndote acceder a la aplicación desde tu navegador en `http://localhost:3000`.

![image-20230907110718983](/home/blackwolf/.config/Typora/typora-user-images/image-20230907110718983.png)

6. Deberías ver que la aplicación Node.js se inicia en el contenedor y está escuchando en el puerto 3000. Puedes acceder a la aplicación en tu navegador web local visitando `http://localhost:3000`.
7. Entramos al contenedor  y verificamos que se halla copiado nuestro proyecto 
   ![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464597640794202/image-20230907112019798.png)

**LISTA DE COMANDOS PARA CONTENEDORES**

1. **Listar todos los contenedores en tu sistema:**

   ```bash
   docker ps -a
   ```

   Este comando mostrará una lista de todos los contenedores en tu sistema, tanto los que están en ejecución como los que están detenidos. Obtendrás detalles como el ID del contenedor, el nombre, el estado, el puerto mapeado y la imagen utilizada.

2. **Ver detalles de un contenedor específico:**

   Para obtener información detallada sobre un contenedor en particular, puedes ejecutar:

   ```bash
   docker inspect nombre-del-contenedor
   ```

   Reemplaza `nombre-del-contenedor` con el nombre o el ID del contenedor que deseas inspeccionar. Esto mostrará una salida JSON con información completa sobre el contenedor.

3. **Ver los registros (logs) de un contenedor:**

   Si deseas ver los registros generados por un contenedor en tiempo real, puedes usar el siguiente comando:

   ```bash
   docker logs nombre-del-contenedor
   ```

   Esto mostrará los registros del contenedor, lo que puede ser útil para depurar o supervisar su comportamiento.

4. **Ver el uso de recursos de un contenedor:**

   Puedes obtener información sobre el uso de recursos, como CPU y memoria, de un contenedor específico con el siguiente comando:

   ```bash
   docker stats nombre-del-contenedor
   ```

   Esto mostrará una tabla en tiempo real con estadísticas de uso de recursos del contenedor.

5. **Limpiar contenedores detenidos:**

   Si deseas eliminar todos los contenedores detenidos en tu sistema, puedes ejecutar:

   ```bash
   docker container prune
   ```

   Esto eliminará todos los contenedores que no están en ejecución, lo que puede ayudar a liberar espacio en disco.

------

**Slide 10: Redes y Volúmenes**

**Gestión de Redes en Docker:**

1. **Redes por defecto:**

   Cuando creas un contenedor, Docker lo conecta automáticamente a una red por defecto llamada "bridge." Esto permite la comunicación entre contenedores en la misma red. Por ejemplo, puedes crear dos contenedores y ver cómo pueden comunicarse entre sí:

   ```bash
   # Crear contenedor2 (el contenedor al que quieres conectarte)
   docker run -d --name contenedor2 ubuntu sleep 3600
   
   # Crear contenedor1 y conectarlo a contenedor2
   docker run -d --name contenedor1 --link contenedor2:alias_contenedor2 ubuntu sleep 3600
   
   # Accede al shell de contenedor1
   docker exec -it contenedor1 /bin/bash
   
   # Desde dentro de contenedor1, actualiza el índice de paquetes y luego instala iputils-ping
   apt update
   apt install iputils-ping -y
   
   ```

   Una vez que hayas instalado `iputils-ping` dentro de `contenedor1`, podrás ejecutar el comando `ping alias_contenedor2` sin problemas para verificar la conectividad con `contenedor2`.

   ![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464597888253983/image-20230907161215254.png)

2. **Creación de redes personalizadas:**

   Puedes crear tus propias redes personalizadas para aislar contenedores o permitir la comunicación entre grupos específicos de contenedores. Por ejemplo, puedes crear una red personalizada y conectar varios contenedores a ella:

   ```bash
   # Crear una red personalizada
   docker network create mi-red-personalizada
   
   # Crear contenedores y conectarlos a la red personalizada
   docker run -d --name contenedor3 --network mi-red-personalizada ubuntu sleep 3600
   docker run -d --name contenedor4 --network mi-red-personalizada ubuntu sleep 3600
   ```

   Los contenedores `contenedor3` y `contenedor4` están en la red personalizada que creaste.
   
   **LISTA DE COMANDOS PARA REDES**
   
   1. **Listar todas las redes en tu sistema:**
   
      ```bash
      docker network ls
      ```
   
      Este comando mostrará una lista de todas las redes en tu sistema Docker, junto con detalles como el nombre, el ID de la red y el controlador de red utilizado.
   
   2. **Ver detalles de una red específica:**
   
      Para obtener información detallada sobre una red en particular, puedes ejecutar:
   
      ```bash
      docker network inspect nombre-de-la-red
      ```
   
      Reemplaza `nombre-de-la-red` con el nombre o el ID de la red que deseas inspeccionar. Esto mostrará una salida JSON con información completa sobre la red.
   
   3. **Crear una nueva red:**
   
      Si deseas crear una nueva red personalizada, puedes usar el siguiente comando:
   
      ```bash
      docker network create nombre-de-la-red
      ```
   
      Esto creará una nueva red con el nombre que especifiques.
   

**Gestión de Volúmenes en Docker:**

1. **Volúmenes de datos:**

   Docker te permite crear volúmenes de datos para almacenar datos de manera persistente. Por ejemplo, puedes crear un volumen y conectarlo a un contenedor:Claro, aquí tienes un paso a paso que integra el ejemplo de creación de un volumen de datos en Docker:

   **Paso 1: Crear un volumen de datos**

   Primero, crea un volumen de datos llamado "mi-volumen" utilizando el siguiente comando:

   ```bash
   docker volume create mi-volumen
   ```

   Esto creará un volumen de datos que Docker utilizará para almacenar datos de manera persistente.

   **Paso 2: Crear un contenedor y conectarlo al volumen**

   Luego, crea un contenedor llamado "contenedor5" y conecta el volumen "mi-volumen" a la ruta "/datos" dentro del contenedor utilizando el siguiente comando:

   ```bash
   docker run -d --name contenedor5 -v mi-volumen:/datos ubuntu sleep 3600
   ```

   Este comando ejecutará un contenedor basado en la imagen "ubuntu" en segundo plano (`-d`). El contenedor tendrá el nombre "contenedor5" (`--name contenedor5`) y se conectará al volumen "mi-volumen" (`-v mi-volumen:/datos`). El contenedor ejecutará el comando "sleep 3600" para mantenerse en ejecución.

   **Paso 3: Verificar la creación del volumen y el contenedor**

   Para verificar que el volumen se ha creado y el contenedor está en ejecución, puedes utilizar los siguientes comandos:

   - Verificar la creación del volumen:

     ```bash
     docker volume ls
     ```

     Esto te mostrará una lista de volúmenes disponibles, y "mi-volumen" debería estar en la lista.

   - Verificar que el contenedor esté en ejecución:

     ```bash
     docker ps
     ```

     Deberías ver una entrada para "contenedor5" en la lista de contenedores en ejecución.

   **Paso 4: Acceder al contenedor y verificar el volumen**

   Puedes acceder al shell del contenedor "contenedor5" para verificar si el volumen se ha montado correctamente y crear un archivo de prueba:

   ```bash
   docker exec -it contenedor5 /bin/bash
   ```

   Una vez dentro del contenedor, puedes verificar la existencia del directorio "/datos" y crear un archivo de prueba:

   ```bash
   # Verificar la existencia del directorio
   ls /datos
   
   # Crear un archivo de prueba
   echo "Hola, mundo!" > /datos/prueba.txt
   
   # Salir del contenedor
   exit
   ```

   **Paso 5: Confirmar la creación del archivo de prueba**

   Finalmente, confirma que el archivo de prueba se haya creado correctamente en el volumen utilizando el siguiente comando fuera del contenedor:

   ```bash
   docker exec contenedor5 cat /datos/prueba.txt
   ```

2. **Volúmenes nombrados:**

   Puedes crear volúmenes nombrados para compartir datos entre múltiples contenedores. Por ejemplo, puedes crear dos contenedores que compartan un volumen nombrado:

   ```bash
   # Crear un volumen nombrado
   docker volume create mi-volumen-nombrado
   
   # Crear dos contenedores que comparten el volumen nombrado
   docker run -d --name contenedor6 -v mi-volumen-nombrado:/datos ubuntu sleep 3600
   docker run -d --name contenedor7 -v mi-volumen-nombrado:/datos ubuntu sleep 3600
   ```

   Los contenedores `contenedor6` y `contenedor7` pueden compartir datos a través del volumen nombrado `mi-volumen-nombrado`.
   
   **LISTA DE COMANDOS PARA VOLÚMENES**
   
   1. **Listar todos los volúmenes en tu sistema:**
   
      ```bash
      docker volume ls
      ```
   
      Este comando mostrará una lista de todos los volúmenes en tu sistema Docker, junto con detalles como el nombre y el controlador de volumen utilizado.
   
   2. **Ver detalles de un volumen específico:**
   
      Para obtener información detallada sobre un volumen en particular, puedes ejecutar:
   
      ```bash
      docker volume inspect nombre-del-volumen
      ```
   
      Reemplaza `nombre-del-volumen` con el nombre o el ID del volumen que deseas inspeccionar. Esto mostrará una salida JSON con información completa sobre el volumen.
   
   3. **Crear un nuevo volumen:**
   
      Si deseas crear un nuevo volumen, puedes usar el siguiente comando:
   
      ```bash
      docker volume create nombre-del-volumen
      ```
   
      Esto creará un nuevo volumen con el nombre que especifiques.
   
   4. **Eliminar un volumen:**
   
      Para eliminar un volumen, utiliza el siguiente comando. Asegúrate de que ningún contenedor esté utilizando el volumen que deseas eliminar.
   
      ```bash
      docker volume rm nombre-del-volumen
      ```
   
      Reemplaza `nombre-del-volumen` con el nombre o el ID del volumen que deseas eliminar.

**Slide 11: Orquestación de Contenedores**

1. Creamos el archvo docker-compose.yml

   

   ```Dockerfile
   version: '3.3'
   
   services:
     postgres:
       image: postgres:13
       environment:
         - POSTGRES_DB=my-prueba-docker
         - POSTGRES_USER=root
         - POSTGRES_PASSWORD=admin123
       ports:
         - 5432:5432
       volumes:
         - ./postgres_data:/var/lib/postgresql/data
   
     pgadmin:
       image: dpage/pgadmin4
       environment:
         - PGADMIN_DEFAULT_EMAIL=admin@mail.com
         - PGADMIN_DEFAULT_PASSWORD=root
       ports:
         - 5050:80
   
   ```

   2.  Ejecuta el siguiente comando para iniciar los servicios definidos en el archivo `docker-compose.yml`:

      ```bash
      docker-compose up -d
      ```

      ![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464598370603118/image-20230907153024768.png)

      - El flag `-d` significa "en segundo plano" y permite que los servicios se ejecuten en segundo plano.

      **Paso 5:** Docker Compose descargará automáticamente las imágenes de los servicios (si no están ya descargadas) y creará los contenedores basados en la configuración proporcionada.

      **Paso 6:** Una vez que todos los contenedores estén en funcionamiento, podrás acceder a los servicios a través de los puertos que se han especificado en el archivo `docker-compose.yml`.

         - PostgreSQL: Puedes acceder a PostgreSQL en `localhost:5432` con las credenciales `POSTGRES_USER` y `POSTGRES_PASSWORD` que se han definido en el archivo.
         - pgAdmin: pgAdmin estará disponible en `localhost:5050`. Puedes iniciar sesión con las credenciales definidas en el archivo.!


   

      2. Cuando hayas terminado de usar los servicios, puedes detenerlos y eliminar los contenedores ejecutando:

   ```bash
   docker-compose down
   ```

   ![img](https://cdn.discordapp.com/attachments/1098583923539320852/1149464598643228672/image-20230907165118907.png)

   Estos pasos te permitirán crear y ejecutar los servicios definidos en tu archivo `docker-compose.yml` para la orquestación de contenedores. Esto facilita la administración y ejecución de múltiples servicios en contenedores y es especialmente útil para entornos de desarrollo o pruebas.

   **COMAMDOS DOCKER-COMPOSE**

   Docker Compose es una herramienta que te permite definir y gestionar aplicaciones multi-contenedor en Docker utilizando un archivo YAML para especificar la configuración de los servicios, volúmenes, redes, etc. Aquí tienes algunos comandos básicos de Docker Compose:

   1. **docker-compose up**: Inicia los servicios definidos en tu archivo `docker-compose.yml`. Si el archivo no se llama `docker-compose.yml`, debes especificar el nombre del archivo con la opción `-f`.

      ```bash
      docker-compose up
      ```

   2. **docker-compose down**: Detiene y elimina los servicios definidos en tu archivo `docker-compose.yml`, así como las redes y volúmenes asociados. Puede ser utilizado con la opción `-v` para eliminar también los volúmenes.

      ```bash
      docker-compose down
      ```

   3. **docker-compose ps**: Muestra el estado de los servicios definidos en tu archivo `docker-compose.yml`.

      ```bash
      docker-compose ps
      ```

   4. **docker-compose logs**: Muestra los logs de los servicios definidos en tu archivo `docker-compose.yml`. Puedes especificar el nombre del servicio si solo deseas ver los logs de un servicio en particular.

      ```bash
      docker-compose logs
      docker-compose logs nombre_del_servicio
      ```

   5. **docker-compose build**: Construye o reconstruye las imágenes de los servicios definidos en tu archivo `docker-compose.yml`.

      ```bash
      docker-compose build
      ```

   6. **docker-compose exec**: Ejecuta un comando dentro de un servicio en ejecución. Puedes especificar el nombre del servicio y el comando a ejecutar.

      ```bash
      docker-compose exec nombre_del_servicio comando_a_ejecutar
      ```

   7. **docker-compose up -d**: Inicia los servicios en modo "detached" (en segundo plano) para que no bloqueen la terminal actual.

      ```bash
      docker-compose up -d
      ```

   8. **docker-compose -f archivo.yml**: Puedes utilizar la opción `-f` para especificar un archivo YAML diferente si no se llama `docker-compose.yml`.

      ```bash
      docker-compose -f mi-archivo.yml up
      ```


**Slide 12: Casos de Uso**

1. **Desarrollo de Aplicaciones en Entornos Aislados:**
   - Los desarrolladores pueden utilizar Docker para crear entornos de desarrollo aislados que reflejen de manera precisa el entorno de producción. Esto evita problemas de "funciona en mi máquina pero no en la tuya" y garantiza que todas las dependencias estén configuradas correctamente.

2. **Despliegue de Aplicaciones en la Nube:**
   - Las plataformas de nube como AWS, Azure y Google Cloud ofrecen soporte para contenedores Docker. Los equipos de desarrollo pueden empaquetar sus aplicaciones en contenedores y luego implementarlas fácilmente en la nube, aprovechando la escalabilidad y la flexibilidad que ofrece Docker.

3. **Orquestación de Microservicios:**
   - Docker se utiliza ampliamente en la arquitectura de microservicios. Cada microservicio se puede ejecutar en su propio contenedor Docker, lo que permite una gestión independiente, escalabilidad y actualización de cada componente de la aplicación. Herramientas como Kubernetes simplifican la orquestación de estos microservicios.

4. **Pruebas y Control de Calidad:**
   - Las pruebas de software se benefician de Docker, ya que se pueden crear entornos de prueba reproducibles y aislados. Los equipos de control de calidad pueden ejecutar pruebas automatizadas en contenedores Docker, lo que garantiza una consistencia en los entornos de prueba.

5. **Implementaciones Rápidas y Escalabilidad:**
   - Docker permite implementaciones rápidas y escalabilidad bajo demanda. Las aplicaciones se pueden dividir en componentes de contenedores que se pueden implementar y escalar independientemente según las necesidades de la carga de trabajo.

6. **Actualización y Gestión de Versiones:**
   - Docker simplifica la gestión de versiones y las actualizaciones de aplicaciones. Los desarrolladores pueden crear nuevas imágenes de contenedores con las últimas actualizaciones y luego implementarlas sin interrupciones.

7. **Portabilidad de Aplicaciones:**
   - Docker garantiza la portabilidad de las aplicaciones. Una vez empaquetada en un contenedor, una aplicación funcionará de manera consistente en cualquier entorno que admita Docker, desde servidores locales hasta entornos de nube.

8. **Entornos de Desarrollo Colaborativo:**
   - Los equipos de desarrollo pueden compartir entornos de desarrollo consistentes mediante contenedores Docker. Esto facilita la colaboración y la resolución de problemas, ya que todos trabajan en el mismo entorno.

9. **Aislamiento y Seguridad:**
   - Docker proporciona un alto nivel de aislamiento entre aplicaciones y garantiza que no haya interferencias entre ellas. Esto mejora la seguridad y la estabilidad de las aplicaciones.

Estos son solo algunos ejemplos de cómo Docker se utiliza en el mundo real para mejorar el desarrollo de aplicaciones, la implementación y la administración de infraestructura de manera eficiente. Su versatilidad y facilidad de uso lo convierten en una herramienta esencial en la industria de la tecnología.

**Slide 14: Buenas Prácticas y Seguridad**

**1. Mantén tus Imágenes y Contenedores Actualizados:**
   - Es responsabilidad de cada miembro del equipo mantener actualizadas sus imágenes y contenedores. Asegúrate de que las imágenes utilizadas sean seguras y se actualicen regularmente.

**2. Usa Docker Bench Security:**
   - Como parte de tu proceso individual, ejecuta Docker Bench Security para evaluar y mejorar la seguridad de tus contenedores. Aporta las mejoras recomendadas a tu entorno.

**3. Limita tus Privilegios de Contenedor:**
   - Cuando configures contenedores, no otorgues privilegios innecesarios. Mantén un enfoque en "el principio del menor privilegio" y asegúrate de que tus contenedores tengan solo los permisos necesarios.

**4. No Ejecutes Contenedores como Usuario Root:**

   - Al crear y ejecutar contenedores, evita ejecutarlos como usuario `root`. Esta es una práctica individual que reduce el riesgo de posibles vulnerabilidades.

**5. Configura las Redes Responsablemente:**
   - Siempre que trabajes con redes de Docker, configura cuidadosamente las políticas de seguridad para limitar la comunicación entre contenedores a lo necesario para tus tareas individuales.

**6. Escanea tus Imágenes:**
   - Antes de utilizar una imagen, realiza un escaneo de seguridad individual para identificar vulnerabilidades conocidas. Esto es importante para proteger tus tareas y proyectos.

**7. Aplica el Principio del Menor Privilegio:**
   - Cuando diseñes tus contenedores y configuraciones, otorga permisos y recursos solo en función de lo que necesites para tu trabajo individual.

**8. Monitorea y Registra tus Contenedores:**
   - Asegúrate de que los contenedores que crees sean monitoreados y registrados adecuadamente. Esto te permitirá mantener un control individual sobre sus actividades y seguridad.

**9. Utiliza Redes Virtuales Aisladas:**
   - Cuando sea relevante para tu trabajo individual, utiliza redes virtuales aisladas para separar contenedores que no necesitan comunicarse. Esto ayuda a mantener la seguridad en tus tareas específicas.

**10. Mantén un Registro de Actividad:**
    - Lleva un registro de tus actividades relacionadas con Docker, como la creación y eliminación de contenedores. Esto te ayudará a mantener un registro individual de tus acciones y eventos de seguridad.

**11. Capacítate:**
    - Como miembro del equipo, asegúrate de estar capacitado en las mejores prácticas de seguridad de Docker. Siempre busca mejorar tu conocimiento y habilidades en seguridad de contenedores.





