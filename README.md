# mysql

```mysql

# una base de datos.
$ mysql -u root -p -t < employees.sql

#Acceder desde un terminal como root a mysql.
$ mysql -u root -p

#Mirar las bases de datos que tenemos.
mysql> SHOW DATABASES;

#Utilizar esa base de datos.
mysql> USE mitabla;

#Mostrar las tablas de la base de datos.
mysql> SHOW TABLES;

#Mostrar la tabla.
mysql> SHOW FIELDS FROM mitabla;

#Mostrar los datos de los empleados.
mysql> SELECT * FROM mitabla;

contar el numero de empleados.
mysql> SELECT COUNT(*) FROM mitabla;

#Mostrar los 10 primeros registros de la tabla.
mysql> SELECT * FROM mitabla LIMIT 10;

#Ordenar alfabéticamente a un numero de personas dado.
mysql> SELECT * FROM mitabla ORDER BY micampo LIMIT 10;

#Sirve para ordenar alfabéticamente a un numero de personas dado ascendentemente A-Z.
mysql> SELECT * FROM mitabla ORDER BY micampo ASC LIMIT 10;

#Ordenar alfabéticamente a un numero de personas dado descendetemente Z-A.
mysql> SELECT * FROM mitabla ORDER BY micampo DESC LIMIT 10;

#Ordenar alfabéticamente a un numero de personas dado empezando despues de la 5a persona.
mysql> SELECT * FROM mitabla ORDER BY micampo LIMIT 10 OFFSET 5;

#Te da el campo con mayor valor de una tabla.
mysql> SELECT MAX (micampo) FROM mitabla;

#Te da el campo con menos valor de una tabla.
mysql> SELECT MIN (micampo) FROM mitabla;

#Saca todos los valores distintos del campo de una tabla.
mysql> SELECT DISTINCT (micampo) FROM mitabla;

#Muestra los 10 primeros valores de todos los campos de la tabla.
mysql> SELECT * FROM mitabla LIMIT 10;

#Muestra los 10 primeros valores de los campos especificados de una tabla.
mysql> SELECT micampo FROM mitabla LIMIT 10;

#Es la suma de campos numericos especificados.
mysql> SELECT SUM (micampo) FROM mitabla;

#Muestra los resultados de una tabla y campo que cumplan determinado requisito.
mysql> SELECT * FROM mitabla WHERE micampo ='Nombre';

#Consultas complejas con la clausula where, muesta los 10 primeros valores que cumplas las condiciones que hemos introducido.(Siempre que se introduzca el valor OR ponerlo entre parentesis).
mysql> SELECT micampo, micampo FROM mitabla WHERE micampo='REQUSITO' OR micampo='REQUISITO_ LIMIT 10;

#OPERADORES PARA CONSULTAS
Tiene que cumplir ambas condiciones.
AND

#Tiene que cumplir una de las condiciones.
OR

#Menor que el otro valor.
<

#Mayor que el otro valor.
>

#Menos o igual que el otro valor.
<=

#Mayor o igual que el otro valor.
>=

#Distinto
<>

#No igual
i=

#Valor nulo
IS NULL

#Valor no nulo
IS NOT NULL

#Introducir un dato en la base de datos (hay que introducirlos en el mismo orden de entrada de datos).
mysql> INSERT INTO mitabla (first_name, last_name, gender, hire_date, birth_date) VALUES('Efren','Moreno','M',2015-02-26',1993-11-20);

#Cambiar datos en la tabla.
mysql> UPTADE mitabla SET micampo='2015-02-26', micampo'1993-11-20' WHERE micampo='Nombre';

#Eliminar datos de la tabla
mysql> DELETE FROM mitabla WHERE micampo='DATO';


```
```php
<?php 

	$servidor = "localhost";
	$usuario = "marcadores";
	$passw = "marcadores";
	$basedatos = "marcadores";

	/**
	 * 	comenzar conexion
	 */
	$conexion = mysql_connect($servidor, $usuario, $passw);

	// fallo la conexion
	if(!$conexion){ die("No se ha podido conectar: " . mysql_error()); }


	/**
	 * 	Crear una BASE DE DATOS
	 */
	// if(mysql_query("CREATE DATABASE primeraBase", $conexion)){
	// 	echo "Se ha creado la Base de Datos";
	// }
	// else {
	// 	echo "No se ha podido crear la base de datos por el siguiente error: " . mysql_error();
	// }


	/**
	 * 	Crear TABLAS en la base de datos
	 */

	// // 1.- seleccionar la base de datos
	// mysql_select_db($basedatos, $conexion);

	// // 2.- preparar comando
	// $sql = "CREATE TABLE Agenda
	// 	(
	// 	personaID int NOT NULL AUTO_INCREMENT,
	// 	PRIMARY KEY(personaID),
	// 	Nombre varchar(15),
	// 	Apellido varchar(15),
	// 	Edad int,
	// 	Telefono int
	// 	)";
	// // 3.- ejecutar la query
	// mysql_query($sql, $conexion);



	/**
	 * 	Crear REGISTROS en la base de datos
	 */

	// 1.- seleccionar la base de datos
	mysql_select_db($basedatos, $conexion);

	// 2.- crea consulta
    $sql = "
    	INSERT INTO Agenda (Nombre, Apellido, Edad, Telefono)
    	VALUES ('Luis', 'Este', 21, 666777888) ";
	
	// 3.- ejecuta la consulta
	//mysql_query($sql, $conexion);



	/**
	 * 	LISTAR REGISTROS de la base de datos
	 */
	mysql_select_db($basedatos, $conexion);

	$sql = "SELECT * FROM Agenda";

	$peticion = mysql_query($sql, $conexion);

	while($fila = mysql_fetch_array($peticion)){
		echo $fila['Nombre']." ". $fila['Apellido']." ". $fila['Edad']." ". $fila['Telefono']."<br>";
	}


	/**
	 * 	CONSULTAR REGISTROS de la base de datos
	 */
	mysql_select_db($basedatos, $conexion);

	$sql = "SELECT * FROM Agenda WHERE Nombre='Manol'";

	$peticion = mysql_query($sql, $conexion);

	while($fila = mysql_fetch_array($peticion)){
		echo $fila['Nombre']." ". $fila['Apellido']." ". $fila['Edad']." ". $fila['Telefono']."<br>";
	}


	/**
	 * 	UPDATE Agenda SET Edad = '24' WHERE Nombre = 'Manol' AND Apellido = 'Vidal'
	 */

	/**
	 * 	DELETE FROM Agenda  WHERE Nombre = 'Manol' AND Apellido = 'Vidal'
	 */


	/**
	* 	terminar conexion
	*/
	mysql_close($conexion);


 ?>
 ```
 
 
 
 ** Pasar datos de PHP a JS
 ```PHP
 <?php 
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>

	// DATOS PARA CONECTAR CON LA BASE DE DATOS
	$servidor = "localhost";
	$usuario = "marcadores";
	$passw = "marcadores";
	$basedatos = "marcadores";


	// 1.-Conectar con la BD
	$conexion = mysql_connect($servidor, $usuario, $passw);
	if(!$conexion){ 
		die("No se ha podido conectar: " . mysql_error()); 
	}
	else {
		echo "conectados a la BD"
	}

	// 2.- Seleccionar la BD con la que vamos a trabajar
	mysql_select_db($basedatos, $conexion);	


	// 3.- Crear la consulta
    $sql = "
    	SELECT * FROM usuarios WHERE DNI='12345678'  
    	";

    // 4.- Ejecutar la consulta
	$peticion = mysql_query($sql, $conexion);


	// 5.- ver resultados
	while( $fila = mysql_fetch_array($peticion) ){
		$dni = $fila['DNI'];
		$nombre = $fila['nombre'];
		$email = $fila['email'];
		$direccion = $fila['direccion'];
	}

	// 6.- Pasar las variables de PHP a Javascript

	echo "<script>
			var dni = '$dni';			
            var nombre = '$nombre';
		</script>";

?>


	<!-- 7.- Usar las variables recien creadas -->
	<script type="text/javascript">

	$(docu ment).ready(function(){

		alert(dni);
		$("#dni").val(dni);


	})

	</script>


	<form>
		<input type="text" name="dni"  placeholer="tu DNI" id="dni">
	</form>
 ```
 
 
