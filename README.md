# ohw2025
OceanHackWeek 2025

Crear un ambiente con las bibliotecas a utilizar
```bash
conda create -n geospatial -c conda-forge python=3.12.3 xarray matplotlib cartopy cmocean -y
```

```bash
conda env create -f environment.yml -n geospatial
```

Comprobar que el entorno tenga ipykernel instalado (necesario para que aparezca como kernel), Instalar y registrar el kernel Jupyter dentro del entorno (esto hace que aparezca en el selector de kernels):

```bash
conda activate geospatial && conda install -n geospatial ipykernel -y
python -m ipykernel install --user --name geospatial --display-name "Python (geospatial)"
```

## Reproducir el entorno `geospatial`

El repositorio incluye `environment.yml` para crear el entorno Conda usado en estos notebooks.

1. Crear el entorno (desde el Codespace o máquina con conda):

```bash
# Inicializar conda para bash (si es necesario)
eval "$(/opt/conda/bin/conda shell.bash hook)"
conda env create -f /workspaces/ohw2025/environment.yml -n geospatial || conda env update -f /workspaces/ohw2025/environment.yml -n geospatial
```

2. Registrar el kernel Jupyter (si no se registró automáticamente):

```bash
/opt/conda/envs/geospatial/bin/python -m ipykernel install --user --name geospatial --display-name "Python (geospatial)"
```

3. En VS Code: abrir el notebook `sst_sample.ipynb`, usar "Select Kernel" y elegir "Python (geospatial)".

## Notas
- El `.devcontainer/devcontainer.json` incluye un `postCreateCommand` que intenta crear/actualizar el entorno y registrar el kernel automáticamente cuando se crea un Codespace.
- Para paquetes pip-only, añádelos bajo la sección `pip:` en `environment.yml`.