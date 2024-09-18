Quelas,Maximiliano
Ingeniería de software III

### TP5 :”Despliegue de aplicaciones con Azure Devops Release Pipelines”

# 1- Objetivos de Aprendizaje
	Adquirir conocimientos acerca de las herramientas de despliegue y releases de aplicaciones.
	
	Configurar este tipo de herramientas.
	
	Comprender el concepto de recurso en Azure
	
	Comprender los conceptos básicos de Release Pipelines en Azure DevOps.
	
	Configurar un Release Pipeline para automatizar despliegues en diferentes entornos-

# 2- Unidad temática que incluye este trabajo práctico
	
	Este trabajo práctico corresponde a la unidad Nº: 3 (Libro Continuous Delivery: Cap 10)

# 3- Consignas a desarrollar en el trabajo práctico:
	
	Los despliegues (deployments) de aplicaciones se pueden realizar en diferentes tipos de entornos
	
	On-Premise (internos) es decir en servidores propios.
	
	Nubes Públicas, ejemplo AWS, Azure, Gcloud, etc.
	
	Plataformas como servicios (PaaS), ejemplo Heroku, Google App Engine, AWS, Azure WebApp, etc
	
	En este práctico haremos despliegue a Plataforma como Servicio utilizando Azure Web Apps

# 4- Desarrollo:

	4.1. Crear una cuenta en Azure

![Descripción de la imagen](Imagen1.png)

	4.2. Crear un recurso Web App en Azure Portal y navegar a la url provista

![Descripción de la imagen](Imagen2.png)
![Descripción de la imagen](Imagen3.png)
![Descripción de la imagen](Imagen4.png)

	4.3. Actualizar Pipeline de Build para que use tareas de DotNetCoreCLI@2 como en el pipeline clásico, luego crear un Pipeline de Release en Azure DevOps con CD habilitada

![Descripción de la imagen](Imagen5.png)
![Descripción de la imagen](Imagen6.png)
![Descripción de la imagen](Imagen7.png)

	4.4. Optimizar Pipeline de Build

![Descripción de la imagen](Imagen8.png)

	4.5. Verificar el deploy en la url de la WebApp /weatherforecast

![Descripción de la imagen](Imagen9.png)

	4.6. Realizar un cambio al código del controlador para que devuelva 7 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio

![Descripción de la imagen](Imagen10.png)
![Descripción de la imagen](Imagen11.png)
![Descripción de la imagen](Imagen12.png)

	4.7. Clonar la Web App de QA para que contar con una WebApp de PROD a partir de un Template Deployment en Azure Portal y navegar a la url provista para la WebApp de PROD.

![Descripción de la imagen](Imagen13.png)
![Descripción de la imagen](Imagen14.png)
![Descripción de la imagen](Imagen15.png)
![Descripción de la imagen](Imagen16.png)
![Descripción de la imagen](Imagen17.png)
![Descripción de la imagen](Imagen18.png)

	4.8. Agregar una etapa de Deploy a Prod en Azure Release Pipelines

![Descripción de la imagen](Imagen19.png)
![Descripción de la imagen](Imagen20.png)

	4.9. Realizar un cambio al código del controlador para que devuelva 10 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast se muestra lo mismo.

![Descripción de la imagen](Imagen21.png)
![Descripción de la imagen](Imagen22.png)
![Descripción de la imagen](Imagen23.png)

	4.10. Modificar pipeline de release para colocar una aprobación manual para el paso a Producción.

![Descripción de la imagen](Imagen24.png)

	4.11. Realizar un cambio al código del controlador para que devuelva 5 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast aun se muestra la versión anterior.

![Descripción de la imagen](Imagen25.png)
![Descripción de la imagen](Imagen26.png)
![Descripción de la imagen](Imagen27.png)

	4.12. Aprobar el pase ya sea desde el release o desde el mail recibido. 
	4.12.1. Notar que se puede dar la aprobación pero posponer su aplicación hasta una determinada fecha

![Descripción de la imagen](Imagen28.png)
![Descripción de la imagen](Imagen29.png)

	4.13. Esperar a la finalización de la etapa de Pase a Prod y luego corroborar que en la url de la webapp_prod/weatherforecast se muestra la nueva versión coinicidente con la de QA. 

![Descripción de la imagen](Imagen30.png)

	4.14. Realizar un pipeline (no release) que incluya el deploy a QA y a PROD con una aprobación manual. El pipeline debe estar construido en YAML sin utilizar el editor clásico de pipelines ni el editor clásico de pipelines de release.

![Descripción de la imagen](Imagen31.png)
![Descripción de la imagen](Imagen32.png)
![Descripción de la imagen](Imagen33.png)
![Descripción de la imagen](Imagen34.png)
![Descripción de la imagen](Imagen35.png)
![Descripción de la imagen](Imagen36.png)
![Descripción de la imagen](Imagen37.png)














