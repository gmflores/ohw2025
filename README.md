# ohw2025

### OceanHackWeek 2025 | Taller intermedio | 6-17 octubre
Jupyter Notebooks de Python para el tratamiento de datos espaciales y temporales

Guillermo Martínez Flores<br>
gmflores@ipn.mx

### Contenido del repositorio
| Archivo | Descripción |
|---|---|
| datos_espaciales.ipynb | Mapas de TSM del NW México |
| datos_espaciales.pdf | Informe generado con `nbconvert` |
| datos_temporales.ipynb | Variación temporal de TSM en el GC |
| datos_temporales.pdf | Informe generado con `nbconvert`|
| environment.yml | Archivo para la instalación de librerías |
| papermill | Directorio con el ejecicio de `papermill`|
| data | Archivos `NetCDF`|
| assets | Archivos complementarios (png) |
|

### Crear un ambiente con las librerías a utilizar

El repositorio incluye `environment.yml` para crear el entorno Conda para ejecutar los scripts:

```bash
conda env create -f environment.yml -n geospatial
```

### Notas

Especificar el ambiente y las librerías individualmente:
>
>```bash
>conda create -n geospatial -c conda-forge python=3.12.3 xarray > matplotlib cartopy cmocean -y
>```

Comprobar que el entorno tenga `ipykernel` instalado (necesario para que aparezca como kernel), Instalar y registrar el kernel Jupyter dentro del entorno (esto hace que aparezca en el selector de kernels):

>```bash
>conda activate geospatial && conda install -n geospatial ipykernel -y
>python -m ipykernel install --user --name geospatial --display-name > "Python (geospatial)"
>```

Registrar el kernel Jupyter (si no se registró automáticamente):

>```bash
>/opt/conda/envs/geospatial/bin/python -m ipykernel install --user --name >geospatial --display-name "Python (geospatial)"
>```

Seleccionar el kernel en VS Code: abrir el notebook, usar "Select Kernel" y elegir "Python (`geospatial`)".

Prueba para crear el entorno (`codespace` | `conda`)

>Inicializar conda para bash

>```bash
>eval "$(/opt/conda/bin/conda shell.bash hook)"
>conda env create -f /workspaces/ohw2025/environment.yml -n geospatial || conda env update -f /workspaces/ohw2025/environment.yml -n geospatial
>```

>El `.devcontainer/devcontainer.json` incluye un `postCreateCommand` que intenta crear/actualizar el entorno y registrar el kernel automáticamente cuando se crea un Codespace.

>En el caso de paquetes pip-only, añádirlos bajo la sección `pip:` en `environment.yml`.
