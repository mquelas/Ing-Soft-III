Quelas,Maximiliano
Ingeniería de software III

### TP8 :”Implementación de Contenedores en Azure y Automatización con Azure CLI”

# 4- Desarrollo:
Prerrequisitos:
Azure CLI instalado

![Descripción de la imagen](Imagen1.png)

	4.1 Modificar nuestro pipeline para construir imágenes Docker de back y front y subirlas a ACR
	Desarrollo del punto 4.1:

		4.1.1 Crear archivos DockerFile para nuestros proyectos de Back y Front
		En la raiz de nuestro repo crear una carpeta docker con dos subcarpetas api y front, dentro de cada una de ellas colocar los dockerfiles correspondientes para la creación de imágenes docker en función de la salida de nuestra etapa de Build y Test image

![Descripción de la imagen](Imagen2.png)
![Descripción de la imagen](Imagen3.png)

		4.1.2 Crear un recurso ACR en Azure Portal siguiendo el instructivo 5.1

![Descripción de la imagen](Imagen4.png)
![Descripción de la imagen](Imagen5.png)

		4.1.3 Modificar nuestro pipeline en la etapa de Build y Test
		Luego de la tarea de publicación de los artefactos de Back agregar la tarea de publicación de nuestro dockerfile de back para que esté disponible en etapas posteriores:

![Descripción de la imagen](Imagen6.png)

		Luego de la tarea de publicación de los artefactos de Front agregar la tarea de publicación de nuestro dockerfile de front para que esté disponible en etapas posteriores:

![Descripción de la imagen](Imagen7.png)

		4.1.4 En caso de no contar en nuestro proyecto con una ServiceConnection a Azure Portal para el manejo de recursos, agregar una service connection a Azure Resource Manager como se indica en instructivo 5.2

![Descripción de la imagen](Imagen8.png)

		4.1.5 Agregar a nuestro pipeline variables

![Descripción de la imagen](Imagen9.png)
![Descripción de la imagen](Imagen10.png)

		4.1.6 Agregar a nuestro pipeline una nueva etapa que dependa de nuestra etapa de Build y Test
		Agregar tareas para generar imagen Docker de Back

![Descripción de la imagen](Imagen11.png)
![Descripción de la imagen](Imagen12.png)
![Descripción de la imagen](Imagen13.png)

		4.1.7 - Ejecutar el pipeline y en Azure Portal acceder a la opción Repositorios de nuestro recurso Azure Container Registry. Verificar que exista una imagen con el nombre especificado en la variable backImageName asignada en nuestro pipeline

![Descripción de la imagen](Imagen14.png)

		4.1.8 - Agregar tareas para generar imagen Docker de Front (DESAFIO)
		A la etapa creada en 4.1.6 Agregar tareas para generar imagen Docker de Front

![Descripción de la imagen](Imagen15.png)
![Descripción de la imagen](Imagen16.png)

		4.1.9 - Agregar a nuestro pipeline una nueva etapa que dependa de nuestra etapa de Construcción de Imagenes Docker y subida a ACR
		Agregar variables a nuestro pipeline:

![Descripción de la imagen](Imagen17.png)

		Agregar variable secreta cnn-string-qa desde la GUI de ADO que apunte a nuestra BD de SQL Server de QA como se indica en el instructivo 5.3

![Descripción de la imagen](Imagen18.png)

		Modificamos nuestro program.cs

![Descripción de la imagen](Imagen19.png)

		Agregar tareas para crear un recurso Azure Container Instances que levante un contenedor con nuestra imagen de back

![Descripción de la imagen](Imagen20.png)

		4.1.10 - Ejecutar el pipeline y en Azure Portal acceder al recurso de Azure Container Instances creado. Copiar la url del contenedor y navegarlo desde browser. Verificar que traiga datos.

![Descripción de la imagen](Imagen21.png)
![Descripción de la imagen](Imagen22.png)
![Descripción de la imagen](Imagen23.png)



		4.1.11 - Agregar tareas para generar un recurso Azure Container Instances que levante un contenedor con nuestra imagen de front (DESAFIO)
		A la etapa creada en 4.1.9 Agregar tareas para generar contenedor en ACI con nuestra 
		Tener en cuenta que el contenedor debe recibir como variable de entorno API_URL el valor de una variable container-url-api-qa definida en nuestro pipeline.
		Para que el punto anterior funcione el código fuente del front debe ser modificado para que la url de la API pueda ser cambiada luego de haber sido construída la imagen. Se deja un ejemplo de las modificaciones a realizar en el repo https://github.com/ingsoft3ucc/CrudAngularConEnvironment.git

![Descripción de la imagen](Imagen24.png)
![Descripción de la imagen](Imagen25.png)
![Descripción de la imagen](Imagen26.png)
![Descripción de la imagen](Imagen27.png)
![Descripción de la imagen](Imagen28.png)


		4.1.12 - Agregar tareas para correr pruebas de integración en el entorno de QA de Back y Front creado en ACI.

![Descripción de la imagen](Imagen29.png)
![Descripción de la imagen](Imagen30.png)


	4.2 Desafíos:

		4.2.4 Agregar etapa que dependa de la etapa de Deploy en ACI QA y genere contenedores en ACI para entorno de PROD.

![Descripción de la imagen](Imagen31.png)
![Descripción de la imagen](Imagen32.png)
![Descripción de la imagen](Imagen33.png)
![Descripción de la imagen](Imagen34.png)
