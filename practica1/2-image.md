![image](https://github.com/JexDev13/2024A-ISWD633-GR2/assets/119013519/84d62854-55e3-4325-9327-cd595fbca558)### Indicaciones para la práctica
El contenido solicitado entre paréntesis angulares debe ser reemplazado y los paréntesis angulares deben ser eliminados.

# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](imagenes/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
# COMPLETAR 

![Imagen y contenedores](imagenes/imagenYcontenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```
Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
# COMPLETAR

```
docker pull hello-world
```
![Imagen y contenedores](imagenes/docker_pull_image.PNG)

**¿Qué es nginx**
# COMPLETAR 

Nginx es un servidor web y proxy inverso de alto rendimiento. Se utiliza para servir contenido estático, equilibrar carga y gestionar conexiones concurrentes. Es conocido por su eficiencia y capacidad de manejar miles de conexiones simultáneas, por lo que sirve para aplicaciones web y sitios de alto tráfico.

Descargar la imagen  **nginx** en la versión **alpine**
# COMPLETAR

```
docker pull nginx:alpine
```

![Imagen y contenedores](imagenes/docker_pull_nginx.PNG)

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

![Imagen y contenedores](imagenes/docker_images.PNG)

**Identificadores**
En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
# COMPLETAR
```
docker inspect hello-world
```

![Imagen y contenedores](imagenes/docker_inspect_1.PNG)
![Imagen y contenedores](imagenes/docker_inspect_2.PNG)

**¿Con qué algoritmo se está generando el ID de la imagen**
# COMPLETAR

Docker utiliza el algoritmo Hash SHA-256 para generar el ID único de cada imagen. 
Cada vez que se crea una nueva imagen o se realiza un cambio en una imagen existente, Docker genera un nuevo ID de imagen utilizando este algoritmo. 

### Filtrar imágenes

```
docker images | grep <termino a buscar>
```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
# COMPLETAR

```
docker rmi hello-world
```

![Imagen y contenedores](imagenes/docker_delete.PNG)

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

