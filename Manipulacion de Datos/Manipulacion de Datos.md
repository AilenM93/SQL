# Manipulacion de Datos

En esta sección de nuestra guía, nos enfocaremos en las consultas de DML (Data Manipulation Language). Estas consultas son fundamentales para la manipulación de los datos almacenados en una base de datos, permitiéndonos realizar operaciones esenciales como insertar, actualizar y eliminar registros. Las habilidades en DML son cruciales para cualquier tester que desee realizar pruebas de datos de manera efectiva y precisa.

## ¿Qué es DML?

DML, o Lenguaje de Manipulación de Datos, es una subcategoría del SQL (Structured Query Language) que se utiliza para gestionar y modificar los datos dentro de las tablas de una base de datos. Las operaciones de DML son clave para interactuar con los datos de una manera que permite su verificación, validación y análisis.

## Importancia de DML para Testers

Para los testers, las consultas de DML son herramientas indispensables por varias razones:

**1. Verificación de Datos:** Probar y validar que los datos insertados, actualizados o eliminados en una aplicación se gestionan correctamente en la base de datos.
**2. Creación de Datos de Prueba:** Generar datos específicos necesarios para escenarios de prueba sin depender de entradas manuales.
**3. Limpieza de Datos:** Eliminar datos innecesarios o crear un entorno limpio y controlado para pruebas repetibles.
**4. Actualización de Estados:** Modificar el estado de registros para simular diferentes condiciones del sistema.

## Estructura de la Sección

En esta sección, cada operación de DML será explicada en detalle, con ejemplos prácticos y escenarios de uso comunes:

**INSERT:** Veremos cómo insertar registros en tablas con valores explícitos.

**UPDATE:** Exploraremos cómo actualizar datos de manera selectiva, utilizando condiciones para asegurar que solo los registros deseados se vean afectados.

**DELETE:** Aprenderemos cómo eliminar registros de forma segura, evitando la eliminación accidental de datos importantes.


Cada subsección proporcionará ejemplos claros y contextualizados, utilizando la base de datos de ejemplo Northwind para ilustrar cómo se aplican estas operaciones en un entorno realista.

Al final de esta sección, deberías sentirte cómodo realizando operaciones de DML, lo que te permitirá gestionar y manipular datos con confianza y precisión en tus tareas de testing. ¡Vamos a empezar!

# INSERT

La cláusula INSERT en SQL se utiliza para agregar nuevos registros a una tabla en una base de datos. Con esta operación, puedes insertar una o más filas de datos en una tabla específica, proporcionando los valores correspondientes para cada columna.

La cláusula INSERT es fundamental porque permite a los usuarios y aplicaciones añadir nuevos datos a la base de datos. Esto es crucial para:

1. Población de Datos: Ingresar datos iniciales o agregar datos nuevos según se generan en tiempo real.
2. Actualización Continua: Mantener la base de datos actualizada con nueva información, como nuevas transacciones, registros de usuarios, pedidos, etc.
3. Pruebas y Desarrollo: Crear datos de prueba para escenarios de testing, permitiendo a los testers verificar la funcionalidad y comportamiento del sistema bajo diferentes condiciones de datos.

El uso de la cláusula INSERT implica especificar la tabla en la que deseas insertar los datos y los valores que deseas agregar. A continuación, se muestran algunos ejemplos de cómo utilizar la cláusula INSERT en SQL.

```sql
INSERT INTO nombre_tabla (columna1, columna2, ...)
VALUES (valor1, valor2, ...)
```

## Consideraciones

1. Los valores insertados deben coincidir con los tipos de datos definidos en la tabla.
2. Si una columna esta definida como NOT NULL, se debe establecer un valor para esa columna.
3. En las tablas donde un columna está definida como AUTO-INCREMENTO, se recomienda no proporcionar valor para esa columna, pues SQL le asignara el valor correspondiente.


## Ejemplo Práctico

A continuacion te mostramos la tabla Shippers de la base de Northwind

| ShipperID | ShipperName | Phone |
| ------------ | ------------ | ------------ |
| 1 |Speedy Express | (503) 555-9831 |
| 2 |United Package | (503) 555-3199 |
| 3 |Federal Shipping | (503) 555-9931 |

Si quisieramos añadir un nuevo registro a la tabla, usariamos:

```sql
INSERT INTO shippers (ShipperName, Phone)
VALUES (Grow North, (503) 555-5462)
```

**NOTA:** En este caso la columna ShipperID esta definida como AUTO-INCREMENTO, por lo que es una buena practica no definir valor para esa columna al insertar nuevos registros

Si quisieramos añadir mas de un registro a la tabla a la misma vez, lo usariamos de l siguiente forma:

```sql
INSERT INTO shippers (ShipperName, Phone)
VALUES
(Hormel Foods, (503) 555- 7452),
(Kepper Exports, (503) 555- 2657),
(Symrise Foods, (503) 555- 9852);
```

Si queremos conocer si los registros se añadieron correctamente, podemos hacer un **SELECT** para consultar todos los registros de la tabla Shippers

```sql
SELECT * FROM shippers 
```

Y debemos obtener la siguiente tabla:

| ShipperID | ShipperName | Phone |
| ------------ | ------------ | ------------ |
| 1 |Speedy Express | (503) 555-9831 |
| 2 |United Package | (503) 555-3199 |
| 3 |Federal Shipping | (503) 555-9931 |
| 4 |Grow North | (503) 555-5462 |
| 5 |Hormel Foods | (503) 555-7452 |
| 6 |Kepper Exports | (503) 555-2657 |
| 7 |Symrise Foods | (503) 555-9852 |
