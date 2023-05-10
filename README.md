# python-web
APP Python WEB

```
------------------------------------------------------------------------------------
Aplicacion WEB - PYTHON
------------------------------------------------------------------------------------
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Frameworks - Librerias:
------------------------------------------------------------------------------------
    - Framework django
    - Framework FlasK: más ligero
      [https://flask.palletsprojects.com/en/2.3.x/installation/]
        - $ pip install Flask (pip administrador de instalaciones de Python)
------------------------------------------------------------------------------------
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Instalaciones:
------------------------------------------------------------------------------------
    > $ python --version
        --> Python 3.11.0

    > $ pip --version
        --> pip 22.3 from C:\Python311\Lib\site-packages\pip (python 3.11)

    - pip install Flask --> Instalar Flask
        --> Collecting Flask
            ...
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Crear Routes para conexion WEB
------------------------------------------------------------------------------------
from flask import Flask
app=Flask(__name__)
@app.route('/')
def home():
    return "Hola Mundo!"
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Levnatra servidor WEB
------------------------------------------------------------------------------------
if __name__=='__main__':
    app.run()
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Correr App:
------------------------------------------------------------------------------------
willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website
    > python index.py
        * Serving Flask app 'index'
        * Debug mode: off
        WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
        * Running on http://127.0.0.1:5000
        Press CTRL+C to quit

Probar en navegadar: http://127.0.0.1:5000
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
HTML:
------------------------------------------------------------------------------------
Agregar carpeta templates e incluir html's
------------------------------------------------------------------------------------
  index.py:
    +> from flask import Flask, render_template
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Levantar el servidor de manera develop (DEBUG) se actualiza cada vez que hay cambios
------------------------------------------------------------------------------------
if __name__=='__main__':
    app.run(debug=True)

Levantar servidor:
===============================================    
$ python index.py
 * Serving Flask app 'index'
 * Debug mode: on
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:5000
Press CTRL+C to quit
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 124-432-451

------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Estilos: CSS
------------------------------------------------------------------------------------
- Agregar carpeta static
    + Agregar carpeta css
        + Agregar archivos de estilos (.css): > website/static/css/main.css
        + Agregar BootStrap 4

------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Agregar cabecera menu - layout:
------------------------------------------------------------------------------------
    - Archivo - layout.html:
        ...
            {% block content %}
            {% endblock %}
        ...

    - Archivo home.html
    {% extends "layout.html" %} 

    {% block content %}
    <h1>Hola Mundo!</h1>
    {% endblock %}
------------------------------------------------------------------------------------
------------------------------------------------------------------------------------
Uso de Colores degradados
------------------------------------------------------------------------------------
  + Uigradients
    - https://uigradients.com/#Blooker20
------------------------------------------------------------------------------------

------------------------------------------------------------------------------------
Desplegar WEB - Heroku:
------------------------------------------------------------------------------------
    - https://www.heroku.com/

    - Separar nuestro entorno virtual:
        - Separar nuestro APP de otros desarrollos.

------------------------------------------------------------------------------------
     > Agregar todo el código dentro de una carpeta src
        * src/static
        * src/template
        * src/index.py
------------------------------------------------------------------------------------
    > Buscar paquete de entornos virtuales de python
      [https://docs.python.org/3/library/venv.html]
      [https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/]

------------------------------------------------------------------------------------
    > pip install virtualenv
        Collecting virtualenv
        Downloading virtualenv-20.23.0-py3-none-any.whl (3.3 MB)
            ---------------------------------------- 3.3/3.3 MB 5.8 MB/s eta 0:00:00
        Collecting distlib<1,>=0.3.6
        Downloading distlib-0.3.6-py2.py3-none-any.whl (468 kB)
            -------------------------------------- 468.5/468.5 kB 9.8 MB/s eta 0:00:00
        Collecting filelock<4,>=3.11
        Downloading filelock-3.12.0-py3-none-any.whl (10 kB)
        Requirement already satisfied: platformdirs<4,>=3.2 in c:\users\willi\appdata\roaming\python\python311\site-packages (from virtualenv) (3.2.0)
        Installing collected packages: distlib, filelock, virtualenv
        WARNING: Failed to write executable - trying to use .deleteme logic
        ERROR: Could not install packages due to an OSError: [WinError 2] El sistema no puede encontrar el archivo especificado: 'C:\\Python311\\Scripts\\virtualenv.exe' -> 'C:\\Python311\\Scripts\\virtualenv.exe.deleteme'


        [notice] A new release of pip available: 22.3 -> 23.1.2
        [notice] To update, run: python.exe -m pip install --upgrade pip

------------------------------------------------------------------------------------
    >  python -m venv venv [correr el modulo venv con el nombre venv de python - recien instalado]
       -> Se genera una carpeta venv copn todo el codigo para correr python solo para mi proyecto o entorno.

------------------------------------------------------------------------------------
    > En este nuevo entorno debo instalar las biblioteca, framewors y librerías que utiulice en mi proyecto  

------------------------------------------------------------------------------------    
    -> willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website
        > venv/Scripts/pip install flask
            Collecting flask
            Using cached Flask-2.3.2-py3-none-any.whl (96 kB)
            Collecting Werkzeug>=2.3.3
            Using cached Werkzeug-2.3.4-py3-none-any.whl (242 kB)
            Collecting Jinja2>=3.1.2
            Using cached Jinja2-3.1.2-py3-none-any.whl (133 kB)
            Collecting itsdangerous>=2.1.2
            Using cached itsdangerous-2.1.2-py3-none-any.whl (15 kB)
            Collecting click>=8.1.3
            Using cached click-8.1.3-py3-none-any.whl (96 kB)
            Collecting blinker>=1.6.2
            Using cached blinker-1.6.2-py3-none-any.whl (13 kB)
            Collecting colorama
            Using cached colorama-0.4.6-py2.py3-none-any.whl (25 kB)
            Collecting MarkupSafe>=2.0
            Using cached MarkupSafe-2.1.2-cp311-cp311-win_amd64.whl (16 kB)
            Installing collected packages: MarkupSafe, itsdangerous, colorama, blinker, Werkzeug, Jinja2, click, flask
            Successfully installed Jinja2-3.1.2 MarkupSafe-2.1.2 Werkzeug-2.3.4 blinker-1.6.2 click-8.1.3 colorama-0.4.6 flask-2.3.2 itsdangerous-2.1.2

            [notice] A new release of pip available: 22.3 -> 23.1.2
            [notice] To update, run: D:\WorkSpace\WS_PYTHON\tutorial\Aplications\website\venv\Scripts\python.exe -m pip install --upgrade pip

    -> se agrego la librería flak a mi proyecto virtual - empaquetado.

------------------------------------------------------------------------------------
    > Levantamos el servidor para probarlo en nuestro entorno virtual:
        -> willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website
            > venv/Scripts/python src/index.py
                * Serving Flask app 'index'
                * Debug mode: on
                WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
                * Running on http://127.0.0.1:5000
                Press CTRL+C to quit
                * Restarting with stat
                * Debugger is active!
                * Debugger PIN: 143-112-127
------------------------------------------------------------------------------------
Entrar en cuenta Heroku - sino tiene crear una:
------------------------------------------------------------------------------------
    - Instalar Heroku cli: si no la tiene para subir App a Heroku.
      [https://devcenter.heroku.com/articles/heroku-cli]

    - Probar la instalacion: 
    > heroku --version (si falla abre nueva consola)

    - Conectarse a Heroku
    > heroku login
------------------------------------------------------------------------------------
    > Crear nueva APP: Por consola:
------------------------------------------------------------------------------------
    - Crear archivo de requerimientos.
        > requirements.txt
                blinker==1.6.2
                click==8.1.3
                colorama==0.4.6
                Flask==2.3.2
                gunicorn==20.1.0
                itsdangerous==2.1.2
                Jinja2==3.1.2
                MarkupSafe==2.1.2
                Werkzeug==2.3.4

    - Crear archivo para decirle la version de python a utilizar (si no se asigna por defecto)
        > runtime.txt
            > python-3.11.0
    
    - Crear archivo para indicar que archivo inicializa el App
        > Procfile
            > web: gunicorn index.app

    NOTA: Instalar completo requerido por Heroku para correr nuestro APP
        [https://gunicorn.org/]

        
    -> willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website
        > venv/Scripts/pip install gunicorn
            Collecting gunicorn
            Downloading gunicorn-20.1.0-py3-none-any.whl (79 kB)
                -------------------------------------- 79.5/79.5 kB 737.1 kB/s eta 0:00:00
            Requirement already satisfied: setuptools>=3.0 in d:\workspace\ws_python\tutorial\aplications\website\venv\lib\site-packages (from gunicorn) (65.5.0)
            Installing collected packages: gunicorn
            Successfully installed gunicorn-20.1.0

            [notice] A new release of pip available: 22.3 -> 23.1.2
            [notice] To update, run: D:\WorkSpace\WS_PYTHON\tutorial\Aplications\website\venv\Scripts\python.exe -m pip install --upgrade pip

    NOTA: Ver la version de python [https://devcenter.heroku.com/articles/python-runtimes]
    ->  willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website
            > venv/Scripts/python --version
                Python 3.11.0 ==> python-3.11.0

    NOTA: Para los requerimientos correr comando de pip
    -> willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website
            > venv/Scripts/pip freeze
                blinker==1.6.2
                click==8.1.3
                colorama==0.4.6
                Flask==2.3.2
                gunicorn==20.1.0
                itsdangerous==2.1.2
                Jinja2==3.1.2
                MarkupSafe==2.1.2
                Werkzeug==2.3.4
------------------------------------------------------------------------------------
Subir mi APP a GIT para subirlo a heroku
------------------------------------------------------------------------------------
    - En la carpeta src
    
    > git init [me genera mi repo]
        -> willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website/src
            > git init  
                Initialized empty Git repository in D:/WorkSpace/WS_PYTHON/tutorial/Aplications/website/src/.git/

    > git add . [agregar mis archivos al repo]

    > git commit -m "iniciar proyecto" [Prepara codigo para subior al remoto]

    > Crear App en Heroku para subir luego los repo desde github
        > heroku create python-web

        -> willi@DESKTOP-M3MBPD8 MINGW64 /d/WorkSpace/WS_PYTHON/tutorial/Aplications/website/src (master)
            > heroku create python-web
                »   Warning: heroku update available from 7.53.0 to 8.1.3.
                Creating python-web... !
                !    To create an app, verify your account by adding payment information.
                !    Verify now at https://heroku.com/verify Learn more at
                !    https://devcenter.heroku.com/articles/account-verification

    > Subir repo a Heroku [https://devcenter.heroku.com/articles/git]
        >heroku git:remote -a  python-web

    > Push a heroku
        > git push heroku main

    WARNING: HEROKU YA NO ES GRATIS...
```

### Salida_

![Captura](https://github.com/wlopera/python-web/assets/7141537/3d767aa1-74ac-4c23-b488-2c7b6a96a007)
![Captura1](https://github.com/wlopera/python-web/assets/7141537/6ee45209-5be4-40ec-adea-f0316092e65a)

