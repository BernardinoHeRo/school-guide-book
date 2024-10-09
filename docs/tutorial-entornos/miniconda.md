# Miniconda

**Miniconda** es una distribución ligera de **Python** que incluye el gestor de paquetes `conda`, permite crear entornos
virtuales (environments) y gestionar paquetes. A diferencia de Anaconda, no viene con paquetes preinstalados, lo que lo hace ideal para
usuarios que buscan un entorno personalizado y ligero. Comúnmente es utilizada en ciencia de datos, aprendizaje
automático y programación en general.

## ¿Cómo se instala en Ubuntu 24.04?

1. Ir al [Sitio oficial de Miniconda](https://docs.conda.io/projects/conda/en/latest/index.html) y descargar la versión
   correspondiente para Ubuntu 24.04.

   ![Miniconda download](./images/instalation.png)
2. Abrir la terminal de Ubuntu 24.04 (`Ctrl + Alt + T`).
3. Dentro de la terminal navega hasta la carpeta donde se almacenó el archivo `.sh` (normalmente se almacena en Downloads/Descargas).
   ```bash
   cd Downloads
   ```
4. Escribimos `ls` para visualizar el nombre del archivo descargado. Supongamos que el archivo descargado se llama
   `Miniconda3-latest-Linux-x86_64.sh`
   ```bash
   ls
   ```
5. Modificar los permisos del archivo para que sea ejecutable:
   ```bash
   chmod +x Miniconda3-latest-Linux-x86_64.sh
   ```
5. Instalar Miniconda ejecutando el script de instalación.
   ```bash
   sudo bash Miniconda3-latest-Linux-x86_64.sh
   ```
   o

   ```bash
   ./Miniconda3-latest-Linux-x86_64.sh
   ```

   (El uso de `sudo` es necesario si no tienes permisos de escritura en la ubicación de instalación).

6. **Seguir las instrucciones en pantalla para completar la instalación.**

7. Una vez instalada, puedes inicializar conda:
   ```bash
   conda init
   ```

8. Cerrar y volver a abrir la terminal para que los cambios surtan efecto.

9. Finalmente, puedes verificar la instalación de Miniconda ejecutando:
   ```bash
   conda --version
   ```

   Esto mostrará la versión de conda instalada en tu sistema, confirmando que la instalación se realizó correctamente.

## Primeros pasos

### Crear un entorno

Para crear un nuevo entorno en Miniconda, puedes usar el siguiente comando:

```bash
conda create --name nombre_del_entorno
```

Por ejemplo, para crear un entorno llamado `mi_entorno`:

```bash
conda create --name mi_entorno
```

### Activar un entorno

Para activar el entorno que has creado, utiliza:

```bash
conda activate mi_entorno
```

### Listar entornos

Para listar todos los entornos que has creado, utiliza el siguiente comando:

```bash
conda env list
```

o

```bash
conda info --envs
```

Esto mostrará una lista de todos los entornos, junto con la ubicación de cada uno.

### Eliminar un entorno

Si deseas eliminar un entorno, utiliza el siguiente comando:

```bash
conda remove --name nombre_del_entorno --all
```

Por ejemplo, para eliminar el entorno `mi_entorno`:

```bash
conda remove --name mi_entorno --all
```

### Verificar el estado del entorno

Para asegurarte de que el entorno ha sido eliminado, puedes volver a listar los entornos:

```bash
conda env list
```

Esto debería mostrar la lista de entornos restantes, confirmando que el entorno ha sido eliminado correctamente.

## Recursos adicionales

- [Documentación de Conda](https://docs.conda.io/projects/conda/en/latest/index.html)
- [Miniconda - Sitio oficial](https://docs.anaconda.com/miniconda/)
- [Tutorial de Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html)
