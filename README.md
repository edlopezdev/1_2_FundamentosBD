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

## Clase 19 de Junio
En esta sesión, profundizaremos aún más en el diseño y manipulación de bases de datos, con un enfoque particular en un sistema de reservaciones para un restaurante. Este escenario nos permitirá abordar desafíos comunes en la gestión de datos relacionados con clientes, reservaciones, mesas, y menús.

Base de Datos: RestauranteV1
Para esta clase, crearemos y utilizaremos la base de datos RestauranteV1, que contendrá tablas para gestionar información sobre clientes, mesas, menús, y las reservaciones.

Estructura de la Base de Datos:
Cliente

ClienteID (Identificador único del cliente)
Nombre (Nombre completo del cliente)
Telefono (Número de teléfono del cliente)
Email (Correo electrónico del cliente)
Mesa

MesaID (Identificador único de la mesa)
Numero (Número de la mesa)
Capacidad (Capacidad máxima de comensales)
Menu

MenuID (Identificador único del menú)
Nombre (Nombre del platillo)
Descripcion (Descripción del platillo)
Precio (Precio del platillo)
Reservacion

ReservacionID (Identificador único de la reservación)
ClienteID (Identificador del cliente que realiza la reservación)
MesaID (Identificador de la mesa reservada)
Fecha (Fecha y hora de la reservación)

## Ejercicios:
Con base en el script de creación de RestauranteV1 y los datos de inserción proporcionados, realiza los siguientes ejercicios:

1. Consulta de Reservaciones por Cliente:
Muestra todas las reservaciones realizadas por el cliente con ID 3.

2. Consulta de Mesas Disponibles:
Muestra todas las mesas que no han sido reservadas para una fecha específica.

3. Actualización de Precio de Menú:
Actualiza el precio del menú con ID 5, incrementándolo en un 10%.

4. Inserción de una Nueva Reservación:
Agrega una nueva reservación para el cliente con ID 2, en la mesa 3, para la fecha "2024-04-30 19:00:00".

5. Eliminación de una Reservación:
Elimina la reservación con ID 4.

## Respuestas de Ejemplo:
1. SELECT * FROM Reservacion WHERE ClienteID = 3;
2. SELECT * FROM Mesa WHERE MesaID NOT IN (SELECT MesaID FROM Reservacion WHERE Fecha = '2024-04-30');
3. UPDATE Menu SET Precio = Precio * 1.10 WHERE MenuID = 5;
4. INSERT INTO Reservacion (ClienteID, MesaID, Fecha) VALUES (2, 3, '2024-04-30 19:00:00');
5. DELETE FROM Reservacion WHERE ReservacionID = 4;

## Ejercicios Avanzados sin Solución:
Explora estos desafíos para una comprensión más profunda:

1. Consulta de Menús Más Populares:
Muestra los menús más reservados, ordenados por popularidad.

2. Optimización de Asignación de Mesas:
Desarrolla una consulta o procedimiento que asigne automáticamente la mesa más pequeña disponible que pueda acomodar el número de comensales.

3. Actualización Masiva de Precios:
Incrementa el precio de todos los menús en un 5% para los platillos con precio mayor a $100.

4. Inserción de un Cliente y su Reservación:
Crea un procedimiento que permita agregar un nuevo cliente y, al mismo tiempo, realizar una reservación para él.

5. Consulta de Reservaciones con Información de Clientes (INNER JOIN):
Muestra todas las reservaciones junto con la información de los clientes correspondientes.

6. Consulta de Todas las Mesas y Sus Reservaciones (LEFT JOIN):
Muestra todas las mesas y las reservaciones asociadas, incluyendo las mesas sin reservaciones.

7. Consulta de Reservaciones sin Clientes (RIGHT JOIN):
Muestra todas las reservaciones que no tienen un cliente asignado.

