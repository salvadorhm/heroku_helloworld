# Configuración básica de Heroku y FastAPI

## 0. Repositorio de GitHub

Como primer paso se crea un repositorio en [GitHub](https://github.com), este servira para llevar el control de cambios en el proyecto y para facilitar el despligue de la aplicación en [Heroku](https://heroku.com).

Una vez creado el repositorio hay que clonarlo para trabajar de forma local o configurar un ambiente de desarrollo en [gitpod](https://gitpod.io) o un [codespace](https://docs.github.com/es/codespaces/overview) de github para agregar los siguientes archivos.

## 1. Lista de Archivos necesarios

Archivos de configuración necesarios para ejecutar la API en [Heroku](https://heroku.com)

|No.|Archivo|Descripción|
|--|--|--|
|1.|.gitignore|[Archivos y directorios](https://github.com/github/gitignore/blob/main/Python.gitignore) que ignoran y que no se suben al repositorio.|
|2.|requirements.txt|[Librerías](https://devcenter.heroku.com/articles/python-pip) necesarias para ejecutar la api.|
|3.|runtime.txt|Versión de [Python](https://devcenter.heroku.com/articles/python-support#specifying-a-python-version) que se usará en Heroku.|
|4.|Procfile|[Configuración](https://devcenter.heroku.com/articles/procfile) de Heroku para ejecutar la api|
|5.|main.py|Hola mundo en [FastAPI](https://fastapi.tiangolo.com/).|
|6.|README.md|Este documento de referencia.|
|7.|LICENSE|[Licencia MIT](https://opensource.org/license/mit/) para el uso del código de este repositorio|

## 2. Ejecución local de la API con gunicorn, uvicorn y fastAPI

Antes de usar Heroku se ejecuta la API de forma local para verificar su funcionamiento utilizando [gunicorn](https://gunicorn.org/) y [uvicorn](https://www.uvicorn.org/).

Referencia para la ejecución de la API en [Heroku](https://heroku.com) [Stackoverflow heroku y fastAPI](https://stackoverflow.com/questions/59391560/how-to-run-uvicorn-in-heroku)

Para este ejemplo se utiliza el puerto 8000 auque puede ser cualquier otro [puerto no asignado](https://www.redeszone.net/tutoriales/configuracion-puertos/puertos-tcp-udp/).

```bash
gunicorn -k uvicorn.workers.UvicornWorker --bind 0.0.0.0:8000 main:app
```
