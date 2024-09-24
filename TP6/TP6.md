Quelas,Maximiliano
Ingeniería de software III

### TP6 :”Pruebas Unitarias”

![Descripción de la imagen](Imagen1.png)

# 4.1 Creación de una BD SQL Server para nuestra App

	A. Crear una BD Azure SQL Database (Ver Instructivo 5.1) o montar una imagen Docker de SQL Server como se solicitó en el punto 12 del [TP02]. 
	(https://github.com/ingsoft3ucc/TPS_2024/blob/main/trabajos/02-introduccion-docker.md)

![Descripción de la imagen](Imagen2.png)

	B. En caso de optar por la opción de montar la imagen de docker, una vez levantada el contenedor, conectarse y ejecutar el siguiente script:

![Descripción de la imagen](Imagen3.png)
![Descripción de la imagen](Imagen4.png)

# 4.2 Obtener nuestra App

	A. Clonar el repo https://github.com/ingsoft3ucc/Angular_WebAPINetCore8_CRUD_Sample.git

![Descripción de la imagen](Imagen5.png)

	B. Seguir las instrucciones del README.md del repo clonado prestando atención a la modificación de la cadena de conexión en el appSettings.json para que apunte a la BD creada en 4.1

![Descripción de la imagen](Imagen6.png)

	C. Navegar a http://localhost:7150/swagger/index.html y probar uno de los controladores para verificar el correcto funcionamiento de la API.

![Descripción de la imagen](Imagen7.png)

	D. Navegar a http://localhost:4200 y verificar el correcto funcionamiento de nuestro front-end Angular image

![Descripción de la imagen](Imagen8.png)

	E. Una vez verificado el correcto funcionamiento de la Aplicación procederemos a crear un proyecto de pruebas unitarias para nuestra API.

![Descripción de la imagen](Imagen9.png)
![Descripción de la imagen](Imagen10.png)

# 4.3 Crear Pruebas Unitarias para nuestra API

	A. En el directorio raiz de nuestro repo crear un nuevo proyecto de pruebas
	unitarias para nuestra API

![Descripción de la imagen](Imagen11.png)

	B. Instalar dependencias necesarias

![Descripción de la imagen](Imagen12.png)

	C. Editar archivo UnitTest1.cs reemplazando su contenido por

![Descripción de la imagen](Imagen13.png)

	D. Renombrar archivo UnitTest1.cs por EmployeeControllerUnitTests.cs

![Descripción de la imagen](Imagen14.png)

	E. Editar el archivo EmployeeCrudApi.Tests/EmployeeCrudApi.Tests.csproj para agregar una referencia a nuestro proyecto de EmployeeCrudApi reemplazando su contenido por

![Descripción de la imagen](Imagen15.png)

	F. Ejecutar los siguientes comandos para ejecutar nuestras pruebas 
	y
	G. Verificar que se hayan ejecutado correctamente las pruebas

![Descripción de la imagen](Imagen16.png)

	I. Modificar la cadena de conexión en el archivo appsettings.json para que use un usuario o password incorrecto y recompilar el proyecto EmployeeCrudApi

![Descripción de la imagen](Imagen17.png)

	J. Verificar que nuestro proyecto ya no tiene acceso a la BD navegando a http://localhost:7150/swagger/index.html y probando uno de los controladores

![Descripción de la imagen](Imagen18.png)

	K. En la carpeta de nuestro proyecto EmployeeCrudApi.Tests volver a correr las pruebas
	y
	L. Verificar que se hayan ejecutado correctamente las pruebas inclusive sin tener acceso a la BD, lo que confirma que es efectivamente un conjunto de pruebas unitarias que no requieren de una dependencia externa para funcionar.

![Descripción de la imagen](Imagen19.png)

	M. Modificar la cadena de conexión en el archivo appsettings.json para que use el usuario y password correcto y recompilar el proyecto EmployeeCrudApi

![Descripción de la imagen](Imagen20.png)

	N. Verificar que nuestro proyecto vuelve a tener acceso a la BD navegando a http://localhost:7150/swagger/index.html y probando uno de los controladores:

![Descripción de la imagen](Imagen21.png)

# 4.4 Creamos pruebas unitarias para nuestro front de Angular:

	A. Nos posicionamos en nuestro proyecto de front, en el directorio EmployeeCrudAngular/src/app

![Descripción de la imagen](Imagen22.png)

	B. Editamos el archivo app.component.spec.ts reemplazando su contenido por:

![Descripción de la imagen](Imagen23.png)

	C. Creamos el archivo employee.service.spec.ts reemplazando su contenido por:

![Descripción de la imagen](Imagen24.png)

	D. Editamos el archivo employee.component.spec.ts ubicado en la carpeta employee reemplazando su contenido por:

![Descripción de la imagen](Imagen25.png)

	E. Editamos el archivo addemployee.component.spec.ts ubicado en la carpeta addemployee reemplazando su contenido por:

![Descripción de la imagen](Imagen26.png)

	F. En el directorio raiz de nuestro proyecto EmployeeCrudAngular ejecutamos el comando

	G. Vemos que se abre una ventana de Karma con Jasmine en la que nos indica que los tests se ejecutaron correctamente

	H. Vemos que los tests se ejecutaron correctamente: 

	I. Verificamos que no esté corriendo nuestra API navegando a http://localhost:7150/swagger/index.html y recibiendo esta salida:

	J. Los puntos G y H nos indican que se han ejecutado correctamente las pruebas inclusive sin tener acceso a la API, lo que confirma que es efectivamente un conjunto de pruebas unitarias que no requieres de una dependencia externa para funcionar.


# 4.5 Agregamos generación de reporte XML de nuestras pruebas de front.

	A. Instalamos dependencia karma-junit-reporter

	B. En el directorio raiz de nuestro proyecto (al mismo nivel que el archivo angular.json) creamos un archivo karma.conf.js con el siguiente contenido

	C. Ejecutamos nuestros test de la siguiente manera:

	D. Verificamos que se creo un archivo test-result.xml en el directorio test-results que está al mismo nivel que el directorio src

# 4.6 Modificamos el código de nuestra API y creamos nuevas pruebas unitarias:

	A. Realizar al menos 5 de las siguientes modificaciones sugeridas al código de la API:

	B. Crear las pruebas unitarias necesarias para validar las modificaciones realizadas en el código

# 4.7 Modificamos el código de nuestro Front y creamos nuevas pruebas unitarias:

	A. Realizar en el código del front las mismas modificaciones hechas a la API.

	B. Las validaciones deben ser realizadas en el front sin llegar a la API, y deben ser mostradas en un toast como por ejemplo https://stackblitz.com/edit/angular12-toastr?file=src%2Fapp%2Fapp.component.ts o https://stackblitz.com/edit/angular-error-toast?file=src%2Fapp%2Fcore%2Frxjsops.ts

	C. Crear las pruebas unitarias necesarias en el front para validar las modificaciones realizadas en el código del front.















