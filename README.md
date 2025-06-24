# Fundamentos de Bases de Datos

**Docente:** Edgar López

## Clase 16 de Junio
En esta sesión, avanzaremos en nuestra comprensión de las bases de datos, centrándonos en consultas más complejas y operaciones de actualización. La sesión está diseñada para brindarte habilidades prácticas en la manipulación de datos para un sistema de gestión de biblioteca.

Base de Datos: BibliotecaV3
Para esta clase, trabajaremos con la base de datos BibliotecaV3, la cual incluye las siguientes tablas y relaciones:

Estructura de la Base de Datos:
Libro

LibroID (Identificador único del libro)
Titulo (Título del libro)
Autor (Autor del libro)
AñoPublicacion (Año de publicación del libro)
Stock (Cantidad disponible en stock)
Prestamo

PrestamoID (Identificador único del préstamo)
LibroID (Identificador del libro prestado)
ClienteID (Identificador del cliente que realiza el préstamo)
FechaPrestamo (Fecha en que se realiza el préstamo)
FechaDevolucion (Fecha en que se devuelve el libro)
Cliente

ClienteID (Identificador único del cliente)
Nombre (Nombre del cliente)
Email (Correo electrónico del cliente)

## Ejercicios:
Basándote en el script de creación de BibliotecaV3 y los scripts de inserción proporcionados, realiza los siguientes ejercicios:

1. Consulta de Préstamos por Cliente:
Muestra todos los préstamos realizados por el cliente con ID 2.

2. Consulta de Libros Prestados:
Muestra todos los libros que actualmente están prestados y no han sido devueltos (FechaDevolucion es NULL).

3. Actualización de Stock de Libro:
Actualiza el stock del libro con ID 4, sumando 2 unidades más.

4. Inserción de un Nuevo Cliente:
Agrega un nuevo cliente a la tabla "Cliente" con los siguientes datos:

Nombre: "Juan Pérez"
Email: "juan.perez@example.com"
5. Eliminación de un Préstamo:
Elimina el préstamo con ID 3 de la tabla "Prestamo".

## Respuestas de Ejemplo:
1. SELECT * FROM Prestamo WHERE ClienteID = 2;
2. SELECT * FROM Prestamo WHERE FechaDevolucion IS NULL;
3. UPDATE Libro SET Stock = Stock + 2 WHERE LibroID = 4;
4. INSERT INTO Cliente (Nombre, Email) VALUES ('Juan Pérez', 'juan.perez@example.com');
5. DELETE FROM Prestamo WHERE PrestamoID = 3;

## Ejercicios Avanzados sin Solución:
Profundiza tu comprensión con estos desafíos:

1. Consulta de Libros Nunca Prestados:
Muestra los libros que nunca han sido prestados.

2. Consulta de Préstamos Expirados:
Muestra todos los préstamos cuya fecha de devolución ha pasado pero el libro no ha sido devuelto.

3. Actualización Masiva de Stock:
Incrementa el stock de todos los libros publicados antes del año 2000 en 5 unidades.

4. Inserción de un Préstamo Completo:
Agrega un nuevo préstamo, incluyendo la actualización del stock del libro prestado, para un cliente existente.

