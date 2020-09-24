# El sistema Conda para administración de paquetes

## Recursos
- Sitio oficial de Conda: [Conda -- Conda documentation](https://conda.io/)
- Comandos para manejo de ambientes en Conda: [Managing environments -- conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
- Tutorial sobre ambientes virtuales de Python: [(Tutorial) Virtual Environment in Python - DataCamp](https://www.datacamp.com/community/tutorials/virtual-environment-in-python)
- Comparación entre Conda y Pip: [Understanding Conda and Pip](https://www.anaconda.com/blog/understanding-conda-and-pip)

## Sistemas administradores de de paquetes
Un [paquete de software](https://es.wikipedia.org/wiki/Paquete_de_software) es un conjunto de programas o bibliotecas, ya sea ejecutables o de código fuente, que se distribuyen conjuntamente. Los paquetes pueden distribuirse a nivel de sistema operativo o de lenguajes de programación. Además del software, los paquetes incluyen otra información importante, como el nombre completo del paquete, una descripción de su funcionalidad, el número de versión, el distribuidor del software, la [suma de verificación (*checksum*)](https://en.wikipedia.org/wiki/Checksum) y una lista de otros paquetes requeridos para el correcto funcionamiento del software. Estos metadatos normalmente se almacenan en una base de datos local.

Un [sistema de administración de paquetes](https://en.wikipedia.org/wiki/Package_manager) es una colección de herramientas que sirven para automatizar el proceso de instalación, actualización, configuración y eliminación de paquetes de software. Algunos ejemplos de sistemas administradores de paquetes son:

- [dpkg](https://wiki.debian.org/Teams/Dpkg): es la base del sistema de gestión de paquetes del sistema operativo [Debian](https://www.debian.org/) y de sus numerosos derivados (ej. [Ubuntu](https://ubuntu.com/)).
- [Homebrew](https://brew.sh/): es un administrador de paquetes para el sistema operativo [macOS](https://www.apple.com/macos) y sistemas [Linux](https://www.linuxfoundation.org/).
- [Chocolatey](https://chocolatey.org/) y [winget](https://github.com/microsoft/winget-cli): son administradores de paquetes para Windows.
- [npm](https://www.npmjs.com/): es un administrador de paquetes para el lenguaje de programación [JavaScript](https://en.wikipedia.org/wiki/JavaScript) y el que utiliza por defecto el entorno de ejecución [Node.js](https://nodejs.org/).
- [pip](https://pip.pypa.io/): es un administrador de paquetes del lenguaje de programación [Python](https://www.python.org/).

## Conda
[Conda](https://docs.conda.io/) es un sistema de administración de paquetes de código abierto que puede ejecutarse en Windows, macOS y Linux. Se distribuye conjutamente con las plataformas para ciencia de datos [Anaconda](https://www.anaconda.com/) y [Miniconda](https://docs.conda.io/en/latest/miniconda.html). Es frecuentemente utilizado para instalar paquetes de Python (como una alternativa a pip), pero también puede instalar paquetes de [C](https://en.wikipedia.org/wiki/C_(programming_language)), [C++](https://isocpp.org/), [R](https://www.r-project.org/) y otros lenguajes de programación o herramientas de software. A diferencia de pip, que instala archivos de código fuente, los paquetes que instala Conda son binarios (i.e. ya están compilados). Estos paquetes se mantienen en repositorios como [repo.anaconda.com](https://repo.anaconda.com/) y [conda-forge](https://anaconda.org/conda-forge).

### Ambientes
Una importante característica de Conda es que permite la creación de ambientes (*environments*) con diferentes versiones de Python, sus bibliotecas o cualquier otro tipo de paquetes. Si, por ejemplo, una aplicación requiere de una versión anterior del interpretador de Python (o de algunos de sus paquetes) Conda permite la creación de un ambiente con esas versiones específicas, sin necesidad de desinstalar las versiones más actualizadas, las cuales pueden funcionar separadamente en otros ambientes.

#### Ejemplos de creación y uso de ambientes
Ejecute los siguientes comandos desde la línea de comandos (*prompt*) de Anaconda.

##### Ambiente para Python 2
A continuación, se crea un ambiente Conda en el que se instala la versión 2 de Python.

**Creación del ambiente**
```shell
# Actualización de Conda
conda update -n base -c defaults conda

# Creación de un ambiente de nombre "python2"
conda create -n python2

# Activación del ambiente
conda activate python2

# Instalación de paquetes
conda install python=2

# Desactivación del ambiente
$ conda deactivate
```

**Uso del ambiente**
```shell
# Activación del ambiente
conda activate python

# Python
python
# Note la versión de Python y salga de la línea de comandos del interpretador con quit()

# Desactivación del ambiente
$ conda deactivate
```

Puede encontrar la referencia de todos los comandos para manejo de ambientes de Conda en:  
[https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).
