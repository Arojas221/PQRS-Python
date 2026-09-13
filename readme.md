1. URL del programa:
a.(en el programa):* Running on http://127.0.0.1:8080
    		   * Running on http://192.168.249.19:8080
b.(Máquina virtual): *
2. Resumen de la funcionalidad
Una página para la gestión PQRS (Peticiones, Quejas, Reclamos, Sugerencias y Denuncias) hecho en python para tanto entidades públicas o privadas fundamental para evaluar la calidad del servicio a cliente. Se pueden crear, editar y borrar peticiones; consultar, responder y editar peticiones enviadas y consultar las métricas y reportes globales de todas las peticiones existentes.
librerías utilizadas (Para reportes y visualizaciones avanzadas):
Pandas.
OpenPyXL.
ReportLab.
Matplotlib.
Técnologías usadas:
HTML5
Bootstrap
CSS Personalizado
MySQL
Flask
3. y 4. Jerarquía del proyecto
├── static
│   ├── \ css
│   │   ├── style.css 
├── templates // diseño de cada ventana
│   ├── base.html
│   ├── dashboard.html
│   ├── editar_pqrsd.html
│   ├── gestion.html
│   ├── index.html
│   ├── login.html
│   ├── nueva_pqrsd.html
│   ├── politica_privacidad.html
│   ├── registro_usuario.html
│   ├── reportes.html
│   ├── responder_pqrs.html
│   ├── tabla_usuarios_registro.html
│   ├── terminos_servicio.html
│   ├── ver_pqrsd.html
├── .deployment
├── .env 
├── app.py // lógica del entorno virtual.
├── config.py // funcionalidades para el backend.
├── models.py // configura la lógica para la base de datos
├── readme.md
├── setup.py
└──sql.txt
\ css
Contiene los diseños hechos en css para las ventanas
templates
Contiene cada una de las ventanas con su estructura y lógica definida usando html.
.env
 configura el entorno hecho en flask.
models.py
Contiene la lógica de la base de datos que se encuentra conectada.
confi.py
configura la lógica para conectarse a la base de datos
sql
contiene la información para poder crear la base de datos en sql
5. configuraciones declaradas en el config.py
DB_HOST = os.getenv("MYSQL_HOST", "localhost") // Define la red a la que se va a conectar
DB_USER = os.getenv("MYSQL_USER", "pqrsd_user") //Define el nombre de usuario
DB_PASSWORD = os.getenv("MYSQL_PASSWORD", "pqrsd_password_2023") // Define la contraseña del usuario
DB_NAME = os.getenv("MYSQL_DB", "sistema_pqrsd") // Define el nombre de la BD
DB_PORT = os.getenv("MYSQL_PORT", "3306")// define el puerto 
6. Paso a paso para ejecutar el proyecto.
a).En el programa
	1. Instalar el lenguaje python en el computador.
	2. Instalar xampo y tener encendida las opciones de apache y MySQL.
	3. Abrir el proyecto en un editor de código como VSC.
	4. Abri SQL e ingresar los scripts del archivo sql.txt para crear la base de datos.
	5. ejecutar en la terminal el comando python app.py.

b).en la máquina virtual y base de datos
	1.Tener instalada una distribución de Linux (ubuntu)
	2. Entrar a la distribución con wsl.
	3. Instalar Azure desde la distribución y crear una cuenta.
		 winget install --exact --id Microsoft.AzureCLI
	4. Crear la base de datos para el programa y desplegarlo.
    az postgres flexible-server create --name "POSTGRES_NOMBRE_INSTANCIA" --resource-group "Grupo de recurso" --admin-user "nombre_admin" --			admin>
	5. desplegar la base de datos en azure
	6. entrar al programa y Configurar el entorno virtual, ingrsando 
		- pip install build
		- python -m build --Wheel (genera el archivo.wlm)
7.Crear la máquina virtual
	az vm create --resource-group "grupo_de_recursos" --name "nombre_vm" --image "Canonical:ubuntu-24_04-lts:server-gen1:latest" --admin-				username "nombreUsuario>

7.Entrar a la máquina virtual:
	-ssh usernam@ipdelavm
8. entrar a la distribución, ubicarse en la carpeta del programa y transferirlo al entorno virtual,
-scp -r Hackaton\ PQRS/ userVM@6IP:/home/jd/
	-./venv/Scripts/actívate
	- pip install flask
	-pip install -r requirements.txt
10. correr la máquina virtual
7.Peticiones
image
8.Base de datos
Imagen de WhatsApp 2025-09-11 a las 11 10 10_091baf6b

Integrante
Juan David samaca Rojas

<!--
proyecto con Jinja2 para usar un template base, uso de bootstrap y separar el CSS en un archivo externo.
-->

# correr el programa

# eliminar entorno virtual antiguo

elimina la carpeta .venv

# -- Entorno virtual

py -m venv .venv

# -- Acceso al entorno virtual

.venv\Scripts\Activate.ps1

pip install flask

# instalar las librerias

pip install -r requirements.txt

# descargar manual si no funciona_____________________________________________________

pip install numpy
pip install matplotlib
pip install kiwisolver
pip install flask
pip install pandas
pip install openpyxl
pip install reportlab
pip install matplotlib
pip install Pillow
pip install kiwisolver

# ejecutar la base de datos______________________________________________________________________________

copiar el sql.txt en tu administrador de base de datos preferida

añadir IMPORTANTE:

ALTER TABLE pqrsd ADD COLUMN respuesta TEXT;

# insertar un funcionario

INSERT INTO usuarios (nombre, email, password, area_id, rol_id)
VALUES ("NOMBRE_FUNCIONARIO", "EMAIL_FUNCIONARIO", "PASSWORD_HASH", "ID_AREA", "ID_ROL_FUNCIONARIO");

EJEMPLO
VALUES ("funcionario1", "emailfuncionario@gmail.com", "123456789", "(1-8)", "2");

# agregar un admin

INSERT INTO usuarios (nombre, email, password, area_id, rol_id)
VALUES ("NOMBRE_ADMIN", "EMAIL_ADMIN", "PASSWORD_HASH", "ID_AREA", "ID_ROL_ADMINISTRADOR");

EJEMPLO
VALUES ("admin", "emailadmin@gmail.com", "123456789", "(1-8)", "1");

# ___________________________________________________________________________________________________

# ejecución

python app.py

## para salir del entorno virtual (.venv)

deactivate

# ------ COMANDOS A TENER EN CUENTA___________________________________________________________________

# para validar y mostrar información detallada del paquete python-dotenv

pip show python-dotenv

# listar las instalaciones

pip list

# Ver ruta de instalación

pip show flask | findstr Location

# para generar un archivo de dependencias

pip freeze > requirements.txt

# para instalar el archivo de dependencias generado

pip install -r requirements.txt

# Actualizar el archivo al agregar paquetes nuevos

pip freeze > requirements.txt


# _____________________________________________________________________________________________________