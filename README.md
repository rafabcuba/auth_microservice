# Microservicio de Autenticación con Django

Este es un microservicio construido con Django que gestiona la autenticación de usuarios utilizando una base de datos PostgreSQL. El servicio utiliza **Django REST Framework** para crear una API RESTful y **JSON Web Tokens (JWT)** para la autenticación segura de los usuarios.

## Características

- Registro de usuarios.
- Inicio de sesión con autenticación basada en JWT.
- Almacenamiento seguro de contraseñas.
- Uso de PostgreSQL como base de datos.

## Requisitos

- Python 3.x
- PostgreSQL
- pip

## Instalación

1. **Clona el repositorio:**

   ```bash
   git clone https://github.com/rafabcuba/auth_microservice.git
   cd nombre_del_repositorio
   ```

2. **Crea y activa un entorno virtual:**

   ```bash
   python -m venv env
   source env/bin/activate  # En Windows usa `env\Scripts\activate`
   ```

3. **Instala las dependencias:**

   Asegúrate de que el archivo `requirements.txt` está en la raíz del proyecto. Luego ejecuta:

   ```bash
   pip install -r requirements.txt
   ```

4. **Configura la base de datos:**

   - Crea una base de datos en PostgreSQL y toma nota de los detalles de conexión (nombre de la base de datos, usuario, contraseña).
   - Crea un archivo `.env` en la raíz del proyecto y añade tus credenciales de la siguiente manera:

     ```plaintext
     DATABASE_NAME='nombre_de_tu_base_de_datos'
     DATABASE_USER='tu_usuario'
     DATABASE_PASSWORD='tu_contraseña'
     DATABASE_HOST='localhost'  # Cambia según tu configuración
     DATABASE_PORT='5432'
     ```

5. **Ejecuta las migraciones:**

   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

## Uso

1. **Ejecuta el servidor de desarrollo:**

   ```bash
   python manage.py runserver
   ```

2. **Registro de Usuario:**

   Realiza una solicitud `POST` a `/api/accounts/register/` con los siguientes datos JSON:

   ```json
   {
       "username": "testuser",
       "password": "testpass"
   }
   ```

3. **Inicio de Sesión:**

   Realiza una solicitud `POST` a `/api/accounts/login/` con los siguientes datos JSON:

   ```json
   {
       "username": "testuser",
       "password": "testpass"
   }
   ```

   Obtendrás tokens de acceso y actualización en la respuesta:

   ```json
   {
       "refresh": "<refresh_token>",
       "access": "<access_token>"
   }
   ```

## Contribuciones

Las contribuciones son bienvenidas. Si deseas contribuir a este proyecto, siéntete libre de abrir un *issue* o enviar un *pull request*.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.

## Contacto

Si tienes preguntas o necesitas más información, puedes contactarme en [rafabcuba@gmail.com].
