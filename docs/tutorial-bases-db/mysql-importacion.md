# Importar base de datos

Después de haber exportado una base de datos a un archivo SQL, puedes importarla a otra base de datos o restaurarla en
la misma. Utiliza el comando `mysql` para llevar a cabo este proceso.

## Comando Básico

El comando básico para importar un archivo SQL a una base de datos es el siguiente:

```bash
mysql -u [usuario] -p nombre_de_la_base_de_datos < /ruta/del/archivo.sql
```

Donde:

* **-u [usuario]**: Especifica el nombre de usuario de MySQL que tiene permisos para importar datos.
* **-p**: Indica que se te pedirá la contraseña del usuario.
  nombre_de_la_base_de_datos: Nombre de la base de datos en la que deseas importar los datos. Debes crear esta base de
  datos previamente si no existe.
* **/ruta/del/archivo.sql**: Redirige el contenido del archivo SQL al comando mysql.

## Ejemplo de Importación

Si tienes un archivo de respaldo llamado backup.sql y deseas importarlo en una base de datos llamada mi_base, el usuario
de tu base de datos es usr, puedes utilizar el siguiente comando:

```bash
mysql -u usr -p mi_base < /ruta/del/backup.sql
```

* *Nota:* Crear la Base de Datos Antes de Importar.

Si la base de datos no existe, primero debes crearla. Para hacerlo, accede al cliente de MySQL con el siguiente
  comando:

```bash
mysql -u usr -p
```

Luego, dentro del cliente de MySQL, crea la base de datos:

```sql
CREATE DATABASE mi_base;
```

Sal del cliente de MySQL escribiendo exit o quit y luego ejecuta el comando de importación como se indicó anteriormente.

## Consideraciones Adicionales
Uso de **--default-character-set**: Si tu archivo SQL utiliza un conjunto de caracteres específico (por ejemplo, UTF-8),
puedes especificarlo con la opción --default-character-set:

```bash
mysql --default-character-set=utf8 -u usr -p mi_base < /ruta/del/archivo.sql
```
## Conclusión
Importar bases de datos con el comando mysql es un proceso sencillo y eficaz para restaurar o transferir datos entre
bases de datos. Asegúrate de que la base de datos de destino exista antes de importar y verifica que tienes los permisos
adecuados para realizar la operación.