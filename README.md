Describe los pasos de instalación y ejecución para que cualquiera pueda ejecutar tu API en su propio entorno, actuando como los "archivos ejecutables", 
ya que la ejecución directa del código es lo que realmente se necesita.

 Gestión de Empleados - API Backend

 Requisitos

- Node.js (v14 o superior)
- MongoDB (Local o MongoDB Atlas)

 Instalación

1. Clona el repositorio:
   bash
   git clone https://github.com/JuanPaperez/DespligueGestionEmp.git
2. Entra en la carpeta del proyecto:
   cd DespligueGestionEmp/Backend
3. Instala las dependencias:
   npm install
4. Configura el archivo .env con tus credenciales de MongoDB:

Crea un archivo .env en la carpeta Backend.
Añade lo siguiente dentro del archivo .env:

MONGODB_URL=<tu-URL-de-conexión-a-MongoDB>

Ejecución en Desarrollo
Inicia el servidor en modo desarrollo:
npm run dev

El servidor estará corriendo en http://localhost:3000.

Ejecución en Producción
Inicia el servidor en modo producción:
npm start

Estructura del Proyecto
Backend/:
controllers/: Contiene la lógica de controladores para las rutas.
models/: Contiene los modelos de la base de datos.
routes/: Define las rutas de la API.
database.js: Configura la conexión a la base de datos MongoDB.
index.js: Archivo principal para iniciar el servidor.
