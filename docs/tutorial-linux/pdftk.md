# Manejo de PDFs

## `pdftk`

`pdftk` es una herramienta de línea de comandos (terminal) para manipular archivos PDF. Permite combinar, dividir,
rotar, cifrar, descifrar y reparar archivos PDF, entre otras operaciones.

### Instalación

Para instalar `pdftk` en Ubuntu:

```bash
sudo apt update
sudo apt install pdftk
```

### Unir varios PDFs en uno solo

Combina múltiples archivos PDF en uno:

```bash
pdftk archivo1.pdf archivo2.pdf archivo3.pdf cat output archivo_unido.pdf
```

### Dividir un PDF en páginas individuales

Divide cada página de un archivo PDF en archivos separados:

```bash
pdftk archivo.pdf burst
```

Esto genera archivos individuales como pg_0001.pdf, pg_0002.pdf, etc.

### Extraer páginas específicas

Extrae un rango de páginas (por ejemplo, de la página 2 a la 4):

```bash
pdftk archivo.pdf cat 2-4 output archivo_paginas.pdf
````

Extrae páginas no consecutivas (páginas 2 y 5):

```bash
pdftk archivo.pdf cat 2 5 output archivo_paginas.pdf
````

Extrae las últimas 5 páginas de un archivo:

```bash
pdftk archivo.pdf cat end-4-end output ultimas_paginas.pdf
````

### Rotar páginas

Rota todas las páginas 90 grados a la derecha:

```bash
pdftk archivo.pdf cat 1-endright output archivo_rotado.pdf
````

Rota la página 2 a la izquierda:

```bash
pdftk archivo.pdf cat 1 2left 3-end output archivo_rotado.pdf
````

Rota todas las páginas 180 grados:

```bash
pdftk archivo.pdf cat 1-enddown output archivo_180.pdf
```

### Añadir contraseña a un PDF

Cifra un archivo PDF y requiere una contraseña para abrirlo:

```bash
pdftk archivo.pdf output archivo_protegido.pdf owner_pw contraseña
````

Añadir una contraseña de usuario para abrir el PDF:

```bash
pdftk archivo.pdf output archivo_protegido.pdf owner_pw contraseña owner_pw contraseña_usuario
```

### Eliminar la contraseña de un PDF

Si conoces la contraseña, puedes eliminarla:

```bash
pdftk archivo_protegido.pdf input_pw contraseña output archivo_sin_contraseña.pdf
```

### Añadir marcas de agua (Watermarks)

Superponer una marca de agua (otro PDF) en todas las páginas del archivo:

```bash
pdftk archivo.pdf background marca_agua.pdf output archivo_marca_agua.pdf
```

Superponer la marca de agua solo en la primera página:

```bash
pdftk archivo.pdf multibackground marca_agua.pdf output archivo_marca_agua.pdf
```

### Rellenar formularios PDF

Rellenar un formulario PDF usando un archivo de datos FDF o XFDF:

```bash
pdftk formulario.pdf fill_form datos.fdf output formulario_relleno.pdf
```

### Fusionar formularios y aplanarlos

Después de rellenar un formulario, puedes aplanarlo para hacer que el contenido sea inmutable:

```bash
pdftk formulario.pdf fill_form datos.fdf output formulario_aplanado.pdf flatten
```

### Añadir archivos adjuntos a un PDF

    Puedes adjuntar otros archivos dentro de un PDF:

```bash
pdftk archivo.pdf attach_files adjunto.txt output archivo_con_adjunto.pdf
```

Eliminar los archivos adjuntos de un PDF:

```bash
pdftk archivo_con_adjunto.pdf unpack_files
```

### Reparar un PDF corrupto

    Si un archivo PDF está dañado o corrupto, pdftk puede intentar repararlo:

```bash
pdftk archivo_corrupto.pdf output archivo_reparado.pdf
```

### Conservar o eliminar metadatos

    Eliminar los metadatos de un PDF:

```bash
pdftk archivo.pdf output archivo_sin_metadatos.pdf
```

Conservar los metadatos de un archivo:

```bash
pdftk archivo.pdf dump_data > metadatos.txt
pdftk archivo.pdf update_info metadatos.txt output archivo_con_metadatos.pdf
```

### Comprimir o reducir tamaño del PDF

Aunque pdftk no tiene una función directa para comprimir PDFs, puedes reducir su tamaño usando otras herramientas en
combinación, como ghostscript:

```bash
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/screen -dNOPAUSE -dQUIET -dBATCH
-sOutputFile=archivo_reducido.pdf archivo.pdf
```

### Combinación avanzada de PDFs (Shuffle)

Puedes mezclar las páginas de varios PDFs, intercalando páginas de diferentes archivos:

```bash
pdftk A=archivo1.pdf B=archivo2.pdf shuffle A B output archivo_mezclado.pdf
```

### Dividir un archivo PDF por tamaño

Dividir un archivo PDF en múltiples archivos más pequeños:

```bash
pdftk archivo.pdf cat 1-100 output parte1.pdf
pdftk archivo.pdf cat 101-200 output parte2.pdf
```

### Crear PDFs criptográficamente seguros

Puedes cifrar un archivo PDF usando una contraseña de propietario y permisos específicos:

```bash
pdftk archivo.pdf output archivo_cifrado.pdf owner_pw contraseña allow Printing
```

### Ver más documentación

> [!NOTE]
> Para ver toda la lista de comandos y opciones disponibles de pdftk, puedes ejecutar:

```bash
pdftk --help
```