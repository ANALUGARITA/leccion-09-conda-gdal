# La biblioteca GDAL para lectura y escritura de datos geoespaciales

## Recursos
* Sitio oficial de GDAL: [GDAL](https://gdal.org/)
* Página oficial de los utilitarios de línea de comandos de GDAL: [Programs -- GDAL documentation](https://gdal.org/programs/)
* Ejemplos de comandos: [Cheat sheet for GDAL/OGR command-line tools](https://github.com/dwtkns/gdal-cheat-sheet)
* Ejemplos de comandos: [GDAL/OGR cheat sheet](https://github.com/glw/gdalcheatsheet)
* Ejemplos de comandos: [OGR2OGR Cheatsheet](https://www.bostongis.com/PrinterFriendly.aspx?content_name=ogr_cheatsheet)

# Características generales
[Geospatial Data Abstraction Library (GDAL)](https://gdal.org/) es una biblioteca para leer y escribir datos geoespaciales en varios formatos [raster](https://gdal.org/drivers/raster/) y [vectoriales](https://gdal.org/drivers/vector/). En ocasiones, también es denominada GDAL/OGR, en donde GDAL se refiere a la funcionalidad para datos raster y OGR (sigla antes usada para *OpenGIS Simple Features Reference Implementation*) a la correspondiente a datos vectoriales. En este documento, se utilizará la sigla GDAL para referirse a ambos casos. GDAL es distribuida por la [Open Source Geospatial Foundation (OSGeo)](https://www.osgeo.org/) con una [licencia X/MIT](https://gdal.org/license.html#license).

GDAL cuenta con un único [modelo abstracto de datos raster](https://gdal.org/user/raster_data_model.html) y un único [modelo abstracto de datos vectoriales](https://gdal.org/user/vector_data_model.html), lo que permite programar aplicaciones geoespaciales sin tener que ocuparse de las particularidades de cada formato que se utilice (GeoTIFF, NetCDF, ESRI Shapefile, GeoJSON, etc.).

A pesar de que GDAL está programada en C/C++, cuenta con una interfaz de programación de aplicaciones (API) para varios lenguajes de programación, incluyendo [C](https://gdal.org/api/index.html#c-api), [C++](https://gdal.org/api/index.html#id3), [Python](https://gdal.org/python/index.html) y [Java](https://gdal.org/java/overview-summary.html). Además, ofrece un conjunto de [utilitarios de línea de comandos](https://gdal.org/programs/) cuyas [distribuciones binarias](https://gdal.org/download.html#binaries) están disponibles para varios sistemas operativos, incluyendo Windows, macOS y Linux. Estas API y los utilitarios también están incluídos en plataforma de ciencia de datos llamada [Anaconda](https://www.anaconda.com/), la cual cuenta con versiones para todos los sistemas operativos mencionados.

## Utilitarios de línea de comandos
Los [utilitarios de línea de comandos de GDAL](https://gdal.org/programs/) permiten ejecutar tareas de geoprocesamiento y de conversión entre formatos geoespaciales sin utilizar una interfaz gráfica o un lenguaje de programación. Están disponibles para varios sistemas operativos, incluyendo Windows, macOS y Unix/Linux.

**Creación del ambiente**  
A continuación, se crea un ambiente Conda en el que se instalan los utilitarios de línea de comandos de GDAL y se presentan varios ejemplos de su uso.
```shell
# Actualización de Conda
conda update -n base -c defaults conda

# Creación de un ambiente de nombre "comandos-gdal"
conda create -n comandos-gdal

# Activación del ambiente
conda activate comandos-gdal

# Instalación de paquetes
# Binarios de GDAL desde el canal conda-forge
conda install -c conda-forge gdal
```

### Consideraciones generales
Los utilitarios de GDAL comparten una serie de [opciones comunes](https://gdal.org/programs/raster_common_options.html#raster-common-options) que pueden visualizarse con la opción `-- help-general`. Por ejemplo:
```shell
ogrinfo --help-general
```
```shell
Generic GDAL utility command options:
  --version: report version of GDAL in use.
  --license: report GDAL license info.
  --formats: report all configured format drivers.
  --format [format]: details of one format.
  --optfile filename: expand an option file into the argument list.
  --config key value: set system configuration option.
  --debug [on/off/value]: set debug level.
  --pause: wait for user input, time to attach debugger
  --locale [locale]: install locale for debugging (i.e. en_US.UTF-8)
  --help-general: report detailed help on general options.
  ```
  
Para obtener ayuda acerca de un comando particular, puede usarse la opción `-- help`. Por ejemplo:
```shell
ogrinfo --help
```
