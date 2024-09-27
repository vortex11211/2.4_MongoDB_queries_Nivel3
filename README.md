# **2.4-MongoDB queries-Nivel3**
El ejercicio nos proporciona una coleción de restaurantes en la ciudad de Nueva York y se nos pide realizar una serie de queries.

Para realizar las consultas que nos indica el ejercicio cargaremos la coleccion de manera local usando MongoCompass

## **Requisitos:**
[MongoDB Community Server]( https://www.mongodb.com/try/download/community "MongoDB Community Server")

En la instalación deseleccionamos la opción `Install MongoD as a Service`
e instalamos **Mongo Compass** en conjunto.

[Mongoshell](https://www.mongodb.com/try/download/shell "Mongoshell")

⚠  _***Importante: una vez instalados habrá que añadirlos como una variable de entorno del sistema**_

Para su instalción puedes seguir este [Video Tutorial](https://www.youtube.com/watch?v=eKXIxSZrJfw "link")


**Descargar los archivos del repositorio**

Base de datos de los restaurantes `restaurants.json`

Consultas asociadas a la base de datos `queries.mongodb`

## Instrucciones para crear la base de Datos y ejecutar las Queries

1. **Montar el servidor local y cargar la base de datos**:
    - En una consola ejecuta el comando `mongod` 
    - Abre `MongoDB Compass`
    - En el `localhost:27017` crearemos una Base de datos usando el archivo  `restaurants.json`.
    en mi caso 

    DatabaseName : `negocios`

    Collection Name: `restaurantes`

    -   `Create Database`

    - Una vez situados en la colección cargaremos el archivo en `add Data`>`Import JSON or CVS file`>`restaurants.json`>`Import`
    

2. **Ejecutar queries**:
    Para ello, instalaremos la extension MongoDB en Visual Studio Code.

    1. **Instala la extensión.**
- 	Abre Visual Studio Code.
- 	Ve a la sección de extensiones (icono de cuadrado en la barra lateral izquierda).
- 	Busca “MongoDB” y selecciona la extensión oficial de MongoDB para instalarla.

    2.**Abre la vista de MongoDB:**
- 	Una vez instalada la extensión, verás un icono de MongoDB en la barra lateral izquierda.
- Haz clic en él para abrir la vista de MongoDB.

    3.	**Añadir una nueva conexión:**
- 	En la vista de MongoDB, haz clic en el botón de `Add Connection` (Añadir Conexión).
- 	Selecciona `Connect with Connection String` (Conectar con cadena de conexión).

    4.**Introduce la cadena de conexión:**
- 	Para una conexión local, usa la siguiente cadena de conexión:
- 	`mongodb://localhost:27017`
- 	Introduce esta cadena en el campo correspondiente y haz clic en `Connect` (Conectar).

    5.**Visualiza las Queries:**
- 	Abre el archivo `queries.mongodb`
- 	Crea otro archivo con la misma extension, **`example.mongodb`**
- 	Ejecuta una a una las consultas, manteniendo el encabezado `use('negocios')` o el nombre que con el que asociaste tu base de datos.
- 	Para ajecutar la consulta simplemente da click en el botón de `run`  ▶  que aparece en la barra superior a la derecha


**Nota**: Para visualizar las queries usando `MongoDB Compass`, simplemente una vez que tengas la base de datos cargada da click en `>_ Open MongoDB shell`
y sustituye en cada una el inicio `db.restaurantes`  por `db["restaurantes"]` o como hayas nombrado tu colección y podrás realizarlas.





