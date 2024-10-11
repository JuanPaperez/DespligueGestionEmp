Manual de Acceso y Ejecución de la API Remota
1. Requisitos Previos
Postman: Debes tener Postman instalado para probar la API.
MongoDB Atlas: La base de datos de empleados está alojada en MongoDB Atlas.
Git: Se usará Git si deseas clonar el proyecto en tu máquina local.
2. Acceder al Proyecto en GitHub
El proyecto se encuentra en GitHub. Para acceder al código fuente:

Clona el repositorio en tu máquina local:

bash
Copiar código
git clone https://github.com/JuanPaperez/DespligueGestionEmp.git
Navega al directorio del backend del proyecto:

bash
Copiar código
cd DespligueGestionEmp/Backend
3. Configuración de Variables de Entorno
El proyecto utiliza un archivo .env para almacenar la URL de conexión a MongoDB Atlas.

Crea un archivo .env en el directorio raíz de tu backend:

bash
Copiar código
touch .env
Dentro del archivo .env, agrega la URL de conexión de MongoDB Atlas:

env
Copiar código
MONGODB_URL=mongodb+srv://<usuario>:<contraseña>@cluster0.sisue.mongodb.net/?retryWrites=true&w=majority
Nota: Reemplaza <usuario> y <contraseña> con tus credenciales de MongoDB Atlas.

4. Instalación de Dependencias
Antes de ejecutar la API, debes instalar todas las dependencias del proyecto. Para ello, ejecuta el siguiente comando:

bash
Copiar código
npm install
5. Conexión con MongoDB Atlas
El proyecto está configurado para conectarse a MongoDB Atlas usando el archivo database.js, el cual utiliza las variables del archivo .env. 
No necesitas modificar nada si ya configuraste correctamente tu archivo .env.

6. Ejecutar el Servidor
Una vez que hayas configurado todo, puedes iniciar el servidor de la API con el siguiente comando:

bash
Copiar código
npm start
Si todo está correcto, deberías ver un mensaje como:

bash
Copiar código
DB is connected
server activo en el puerto 3000
7. Probar la API con Postman
Endpoints Disponibles:
Obtener todos los empleados (GET)

URL: http://localhost:3000/api/empleados
Método: GET
Crear un empleado (POST)

URL: http://localhost:3000/api/empleados
Método: POST
Cuerpo:
json
Copiar código
{
  "name": "Juan Perez",
  "position": "Desarrollador",
  "office": "Bogotá",
  "salary": 5000
}
Obtener un empleado por ID (GET)

URL: http://localhost:3000/api/empleados/{id}
Método: GET
Actualizar un empleado por ID (PUT)

URL: http://localhost:3000/api/empleados/{id}
Método: PUT
Cuerpo:
json
Copiar código
{
  "name": "Juan Perez",
  "position": "Desarrollador Senior",
  "office": "Bogotá",
  "salary": 6000
}
Eliminar un empleado por ID (DELETE)

URL: http://localhost:3000/api/empleados/{id}
Método: DELETE
8. Verificación en MongoDB Atlas
Puedes verificar que los empleados se están almacenando correctamente en la base de datos conectándote a MongoDB Atlas. 
En la colección de empleados de tu base de datos, deberías ver los registros que has creado a través de Postman.

Estructura del Proyecto
Backend/:
controllers/: Contiene la lógica de controladores para las rutas.
models/: Contiene los modelos de la base de datos.
routes/: Define las rutas de la API.
database.js: Configura la conexión a la base de datos MongoDB.
index.js: Archivo principal para iniciar el servidor.
