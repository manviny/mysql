# mysql

```mysql
# sirve para acceder desde un terminal como root a mysql
$ mysql -u root -p
#sirve para mirar las bases de datos que tenemos
$ SHOW DATABASES
```
mysql -u root -p (sirve para acceder desde un terminal como root a mysql).
SHOW DATABASES (sirve para mirar las bases de datos que tenemos).
USE (NOMBRE DE LA TABLA) (sirve para utilizar esa base de datos).
SHOW TABLES (sirve para mostrar las tablas de la base de datos).
SHOW FIELDS FROM (NOMBRE DE LA TABLA) (sirve para mostrar la tabla).
SELECT * FROM employees (sirve para mostrar los datos de los empleados).
SELECT COUNT(*) FROM employees (sirve para contar el numero de empleados).
SELECT * FROM employees LIMIT 10 (sirve para mostrar los 10 primeros registros de la tabla).
SELECT * FROM employees ORDER BY first_name LIMIT 10 ( sirve para ordenar alfabéticamente a un numero de personas dado).
SELECT * FROM employees ORDER BY first_name ASC LIMIT 10 ( sirve para ordenar alfabéticamente a un numero de personas dado ascendentemente A-Z).
SELECT * FROM employees ORDER BY first_name DESC LIMIT 10 ( sirve para ordenar alfabéticamente a un numero de personas dado descendetemente Z-A).
SELECT * FROM employees ORDER BY first_name LIMIT 10 OFSET 5 ( sirve para ordenar alfabéticamente a un numero de personas dado empezando despues de la 5a persona).
