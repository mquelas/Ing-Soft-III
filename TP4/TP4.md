Quelas,Maximiliano
Ingeniería de software III

### TP4 :”Pipeline”

# 1- Objetivos de Aprendizaje
Adquirir conocimientos acerca de las herramientas de integración continua presentes en ADO.
Configurar este tipo de herramientas.
Implementar procesos de construcción automatizados simples.

# 2- Unidad temática que incluye este trabajo práctico
Este trabajo práctico corresponde a la unidad Nº: 3 (Libro Continuous Delivery: Cap 3)

CI (Continuous Integration), Continuous Deployment y Continuous Delivery son tres prácticas clave en la ingeniería de software que se utilizan para mejorar la calidad del software y acelerar el proceso de desarrollo. Aunque están relacionadas y a menudo se utilizan juntas, tienen diferencias clave:

Continuous Integration (CI):

CI es una práctica que implica la integración constante de cambios de código en un repositorio compartido por parte de varios desarrolladores. Los desarrolladores envían regularmente su código al repositorio compartido (a menudo varias veces al día). Cada vez que se envía código, se activan pruebas automáticas para verificar la calidad y la compatibilidad del código. El objetivo principal de CI es detectar y resolver problemas de integración de código de manera temprana y continua, lo que evita la acumulación de errores.

Continuous Delivery En Continuous Delivery, después de que el código pasa por CI y se considera estable, se automatiza el proceso de empaquetado y preparación para la entrega. Sin embargo, la entrega real al entorno de producción se realiza manualmente después de una revisión y aprobación humanas.

Continuous Deployment (CD) Se refiere a la práctica de automatizar y acelerar el proceso de entrega de software al entorno de producción. En Continuous Development, una vez que el código pasa por el proceso de CI y se considera estable, se automatiza la entrega del software al entorno de producción sin intervención manual adicional. Esto implica la automatización de tareas como pruebas adicionales, empaquetado, despliegue y configuración en el entorno de producción.

En resumen, CI se centra en la integración continua de cambios de código y pruebas automáticas, mientras que Continuous Delivery y Continuous Deployment se centran en la automatización del proceso de entrega de software al entorno de producción, con Continuous Delivery deteniéndose antes de la entrega real y Continuous Deployment automatizando todo el proceso hasta la entrega al entorno de producción. Estas prácticas son esenciales en el desarrollo de software ágil y permiten la entrega rápida y confiable de software de alta calidad.

# 3- Consignas a desarrollar en el trabajo práctico:
Azure DevOps Pipelines
Breve descripción de Azure DevOps Pipelines:

--Azure DevOps Pipelines es un servicio de CI/CD para compilar, probar y desplegar aplicaciones de forma automatizada.

Tipos de Pipelines: Build y Deploy:

--Build Pipelines: Compilan el código y crean artefactos listos para desplegar.

--Deploy Pipelines: Despliegan artefactos en diferentes entornos (desarrollo, pruebas, producción).

Diferencias entre editor clásico y YAML:
	
--Editor Clásico: Interfaz gráfica fácil de usar, menos flexible.

--YAML: Pipelines como código, más flexible, requiere conocimientos básicos de scripting.

Agentes MS y Self-Hosted:

--Microsoft-Hosted Agents: Mantenidos por Microsoft, fáciles de usar, con limitaciones de recursos.

--Self-Hosted Agents: Configurados por el usuario, mayor control y flexibilidad, requieren mantenimiento.

# 4- Pasos del TP
4.1 Verificar acceso a Pipelines concedido
![Descripción de la imagen](Imagen1.png)
![Descripción de la imagen](Imagen2.png)


4.2 Agregar en pipeline YAML una tarea de Publish.
![Descripción de la imagen](Imagen3.png)
![Descripción de la imagen](Imagen4.png)



4.3 Explicar por qué es necesario contar con una tarea de Publish en un pipeline que corre en un agente de Microsoft en la nube.

--Persistencia de Artefactos: Guarda los archivos generados durante la construcción para su uso posterior.

--Separación de Fases: Separa la construcción del despliegue, permitiendo que los artefactos se usen en diferentes etapas.

--Despliegue en Múltiples Entornos: Permite desplegar los mismos artefactos en entornos de staging y producción.

--Auditoría y Trazabilidad: Facilita el seguimiento de versiones específicas y su correlación con el código fuente.

--Colaboración entre Pipelines: Los artefactos publicados pueden ser reutilizados en otros pipelines o etapas.

4.4 Descargar el resultado del pipeline y correr localmente el software compilado.
![Descripción de la imagen](Imagen5.png)


4.5 Habilitar el editor clásico de pipelines. Explicar las diferencias claves entre este tipo de editor y el editor YAML.

![Descripción de la imagen](Imagen6.png)

-Un editor de texto general es versátil y puede manejar una variedad de formatos y lenguajes, un editor YAML específico está optimizado para trabajar con la estructura y sintaxis particular del formato YAML, proporcionando herramientas y características especializadas para este propósito.

4.6 Crear un nuevo pipeline con el editor clásico. Descargar el resultado del pipeline y correr localmente el software compilado.

![Descripción de la imagen](Imagen7.png)
![Descripción de la imagen](Imagen8.png)
![Descripción de la imagen](Imagen9.png)
![Descripción de la imagen](Imagen10.png)


4.7 Configurar CI en ambos pipelines (YAML y Classic Editor). Mostrar resultados de la ejecución automática de ambos pipelines al hacer un commit en la rama main.

Classic Editor:

![Descripción de la imagen](Imagen11.png)

YAML:

![Descripción de la imagen](Imagen12.png)
![Descripción de la imagen](Imagen13.png)


4.8 Explicar la diferencia entre un agente MS y un agente Self-Hosted. Qué ventajas y desventajas hay entre ambos? Cuándo es conveniente y/o necesario usar un Self-Hosted Agent?

--Agentes MS (Microsoft-hosted):
	
	Ventajas: Mantenimiento automático, no requiere configuración.
	Desventajas: Menos control, tiempos de ejecución limitados.

--Agentes Self-Hosted:
	
	Ventajas: Control total, mejor rendimiento, posible ahorro.
	Desventajas: Necesita mantenimiento y configuración.

--Uso de Self-Hosted: Cuando necesitas un entorno personalizado, mayor rendimiento o tienes alta demanda de construcción.

4.8 Crear un Pool de Agentes y un Agente Self-Hosted

![Descripción de la imagen](Imagen14.png)
![Descripción de la imagen](Imagen15.png)


4.9 Instalar y correr un agente en nuestra máquina local.

![Descripción de la imagen](Imagen16.png)
![Descripción de la imagen](Imagen17.png)
![Descripción de la imagen](Imagen18.png)


4.10 Crear un pipeline que use el agente Self-Hosted alojado en nuestra máquina local.

![Descripción de la imagen](Imagen19.png)
![Descripción de la imagen](Imagen20.png)


4.11 Buscar el resultado del pipeline y correr localmente el software compilado.

![Descripción de la imagen](Imagen21.png)


4.12 Crear un nuevo proyecto en ADO clonado desde un repo que contenga una aplicación en Angular como por ejemplo https://github.com/ingsoft3ucc/angular-demo-project.git

![Descripción de la imagen](Imagen22.png)
![Descripción de la imagen](Imagen23.png)

4.13 Configurar un pipeline de build para un proyecto de tipo Angular como el clonado.

![Descripción de la imagen](Imagen24.png)
![Descripción de la imagen](Imagen25.png)


4.14 Habilitar CI para el pipeline.

![Descripción de la imagen](Imagen26.png)


4.15 Hacer un cambio a un archivo del proyecto (algún cambio en el HTML que se renderiza por ejemplo) y verificar que se ejecute automáticamente el pipeline.

![Descripción de la imagen](Imagen27.png)
![Descripción de la imagen](Imagen28.png)


4.16 Descargar el resultado del pipeline y correr en un servidor web local el sitio construido.

![Descripción de la imagen](Imagen29.png)
![Descripción de la imagen](Imagen30.png)
![Descripción de la imagen](Imagen31.png)


4.17 Mostrar el antes y el después del cambio.
		
		Como se puede ver se le agrego una barra de search

![Descripción de la imagen](Imagen32.png)



# 5- Presentación del trabajo práctico.
Subir un doc al repo con las capturas de pantalla de los pasos realizados y colocar en el excel de repos (https://docs.google.com/spreadsheets/d/1mZKJ8FH390QHjwkABokh3Ys6kMOFZGzZJ3-kg5ziELc/edit?gid=0#gid=0) la url del proyecto de AzureDevops.

# 6- Criterio de Calificación
Los pasos 4.1 al 4.11 representan un 60% de la nota total, los pasos 4.12 al 4.17 representan el 40% restante



