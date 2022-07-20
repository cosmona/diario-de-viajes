# Plataforma diario de viajes

- Se trata de una web donde los usuarios publican entrada sobre viajes
- Cada entrada tiene un título, descripción, lugar y hasta 3 fotos asociadas
- Cada entrada puede ser votada con una puntuación entre 1 y 5

API Endpoints:

Entradas de diario:

- GET - /entries - JSON con lista todas las entradas y buscar entradas | Sin token
- GET - /entries/:id - JSON que muestra información de una entrada | Sin token
- POST - /entries - crea una entrada | Token obligatorio
- PUT - /entries/:id - edita el lugar o descripción de una entrada | Token obligatorio y mismo usuario (o admin) pero sólo un tiempo determinado despues de crearla
- DELETE - /entries/:id - borra una entrada | Token obligatorio y mismo usuario (o admin)
- POST - /entries/:id/photos - añade una imagen a una entrada | Token obligatorio y mismo usuario (o admin)
- DELETE - /entries/:id/photos/:photoID - borra una imagen de una entrada | Token obligatorio y mismo usuario (o admin)
- POST - /entries/:id/votes - vota una entrada | Token obligatorio pero cada usuario solo puede votar una vez y las entradas no pueden ser votadas por el usuario que las creó

Usuarios:

- POST - /users - Crear un usuario pendiente de activar
- GET - /users/validate/:registrationCode - Validará un usuario recien registrado
- POST - /users/login - Hará el login de un usuario y devolverá el TOKEN
- GET - /users/:id - Devolver información del usuario | Token obligatorio y si el usuario coincide dar más información
- DELETE - /users/:id - Borrar un usuario | Solo lo puede hacer el admin
- PUT - /users/:id - Editar un usuario (name, email, avatar) | Solo el propio usuario
- PUT - /users/:id/password - Editar la contraseña de un usuario | Solo el propio usuario
- POST /users/recover-password
- POST /users/reset-password
