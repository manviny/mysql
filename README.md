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
