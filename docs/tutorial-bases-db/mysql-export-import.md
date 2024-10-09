# Exportar con mysqldump

`mysqldump` es una utilidad de MySQL que permite exportar bases de datos a un archivo de texto en formato SQL. Este
archivo puede ser utilizado para crear una copia de seguridad de la base de datos o para transferirla a otro servidor. A
continuación, se presentan los pasos para exportar una base de datos, incluyendo cómo ignorar tablas específicas y
exportar solo datos.

## Comando Básico

El comando básico para exportar una base de datos, incluyendo todas sus tablas e información, es el siguiente:

```bash
mysqldump -u [usuario] -p nombre_de_la_base_de_datos > /ruta/de/almacenamiento/nombre_archivo.sql
```

* **-u [usuario]**: Especifica el nombre de usuario de MySQL.
* **-p**: Indica que se te pedirá la contraseña del usuario.
* **nombre_de_la_base_de_datos**: Nombre de la base de datos que deseas exportar.
* **/ruta/de/almacenamiento/nombre_archivo.sql**: Redirige la salida del comando a un archivo SQL en la ruta
  especificada.

## Ejemplo de Exportación

Para exportar una base de datos llamada **mi_base** que pertenece al usuario: **usr** y guardar el archivo en una ruta
específica, se hace de la siguiente manera:

```bash
mysqldump -u usr -p mi_base > /ruta/de/almacenamiento/respaldo_$(date +"%Y%m%d_%H%M%S").sql
```

Este comando crea un archivo con el nombre de **respaldo** con la fecha y hora actual (respaldo_$(date +"%Y%m%d_%H%M%S")
.sql) en el
nombre.

### Ignorar Tablas Específicas

Si deseas exportar una base de datos pero ignorar ciertas tablas, puedes utilizar la opción **--ignore-table**. El
comando
tendría el siguiente formato:

```bash
mysqldump -u [usuario] -p --ignore-table=nombre_de_la_base_de_datos.nombre_de_la_tabla1 --ignore-table=nombre_de_la_base_de_datos.nombre_de_la_tabla2 nombre_de_la_base_de_datos > /ruta/al/archivo.sql
```

* **--ignore-table=nombre_de_la_base_de_datos.nombre_de_la_tabla**: Especifica la tabla que deseas ignorar durante la
  exportación.
  Ejemplo
  Si quieres exportar mi_base_de_datos pero ignorar las tablas usuarios y pedidos, el comando sería:

```bash
mysqldump -u [usuario] -p --ignore-table=mi_base_de_datos.usuarios --ignore-table=mi_base_de_datos.pedidos
mi_base_de_datos > /home/behero/Videos/DEVELOPMENT/BACKEND-ZONACOOL/database-configuration/backup_$(date +"%Y%m%d_
%H%M%S").sql
```

### Exportar Solo Datos

Si prefieres exportar solo los datos de las tablas y no la estructura (definiciones de tabla), puedes utilizar la opción
**--no-create-info**. Esto es útil si ya tienes la estructura de la base de datos creada en otro lugar y solo deseas
transferir los datos.

```bash
mysqldump -u [usuario] -p --no-create-info nombre_de_la_base_de_datos > /ruta/al/archivo.sql
```

Ejemplo
Para exportar solo los datos de mi_base_de_datos:

```bash
mysqldump -u [usuario] -p --no-create-info mi_base_de_datos >
/home/behero/Videos/DEVELOPMENT/BACKEND-ZONACOOL/database-configuration/backup_datos_$(date +"%Y%m%d_%H%M%S").sql
```

## Conclusión

Exportar bases de datos con **mysqldump** es una herramienta esencial para la gestión de datos en MySQL. Al utilizar las
opciones adecuadas, puedes personalizar tu exportación para incluir o excluir tablas y decidir si deseas exportar solo
los datos. Esto te proporciona flexibilidad en la administración y respaldo de tus bases de datos.