# WHERE y los Operadores

La cláusula **WHERE** en SQL se utiliza para filtrar registros de una tabla según condiciones específicas, y los operadores juegan un papel crucial al definir estas condiciones. Los operadores permiten crear expresiones complejas y precisas dentro de la cláusula WHERE. Juntos, WHERE y los operadores proporcionan la capacidad de seleccionar, actualizar o eliminar únicamente aquellos registros que cumplen con criterios detallados, mejorando así la precisión y eficiencia de las consultas en una base de datos.


```sql
SELECT columna1, columna2, ...
FROM nombre_de_la_tabla
WHERE condición;
```

## Tipos de Operadores

### De comparación

Los operadores de comparación en SQL se utilizan para comparar dos valores y devolver un resultado booleano (TRUE o FALSE). Son esenciales para construir condiciones dentro de la cláusula WHERE y otras expresiones lógicas en SQL. A continuación se describen los operadores de comparación más comunes:

| Operador | Significado |
| ------------ | ------------ |
| = | Igual a |
| != o <> | Distinto de |
| < | Menor que|
| <= | Menor o igual que |
| > | Mayor que |
| >= | Mayor o igual que |



**Ejemplo Práctico**

La base de datos Northwind tiene una tabla llamada Products que contiene información sobre los productos. Aquí tienes un resumen de dicha tabla:

| ProductID | ProductName | SupplierID | CategoryID | Unit | Price |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| 1 | Aniseed Syrup | 1 | 2 | 12 - 550 ml bottles | 10 |
| 2 | Mishi Kobe Niku | 4 | 4 | 18 - 500 g pkgs. | 48 |
| 3 | Queso Cabrales | 5 | 4 | 1 kg pkg. | 5 |
| 4 | Carnarvon Tigers | 7 | 8 | 16 kg pkg. | 63 |
| 5 | Mascarpone Fabioli | 14 | 4 | 24 - 200 g pkgs. | 32 |
| 6 | Côte de Blaye | 18 | 1 | 12 - 75 cl bottles | 264 |

1. Seleccionar productos cuyo precio por unidad es exactamente 48:

```sql
SELECT * FROM Products
WHERE Price = 48;
```

2. Seleccionar productos cuyo precio por unidad no es 264:

```sql
SELECT ProductID, ProductName, Price
FROM Products
WHERE Price != 264;
```

3. Seleccionar productos cuyo precio por unidad es mayor o igual a 20:

```sql
SELECT ProductID, ProductName, Price
FROM Products
WHERE Price >= 20;
```

  
### Lógicos (AND, OR, NOT)

Los operadores lógicos en SQL se utilizan para combinar múltiples condiciones en la cláusula WHERE, HAVING, y otras partes de una consulta SQL. Permiten realizar evaluaciones más complejas y precisas sobre los datos al determinar si una o varias condiciones son verdaderas o falsas.

**Principales Operadores Lógicos**

**1. AND:** Combina dos o más condiciones y devuelve TRUE solo si todas las condiciones son verdaderas.

```sql
SELECT columna1, columna2, ...
FROM nombre_de_la_tabla
WHERE condición AND condición;
```

**2. OR:** Combina dos o más condiciones y devuelve TRUE si al menos una de las condiciones es verdadera.

```sql
SELECT columna1, columna2, ...
FROM nombre_de_la_tabla
WHERE condición OR condición;
```

**3. NOT:** Invierte el resultado de una condición. Devuelve TRUE si la condición es falsa y viceversa

```sql
SELECT columna1, columna2, ...
FROM nombre_de_la_tabla
WHERE NOT condición;
```

 **Ejemplo Práctico**
 
Supongamos que queremos seleccionar productos que cumplen con las siguientes condiciones:

1. Los productos tienen un precio (Price) mayor a 20 y su categoria (CategoryID) es igual a 4.
2. O, los productos son de categoria (CategoryID) es igual a 2

La consulta SQL utilizando operadores lógicos sería la siguiente:

```sql
SELECT ProductID, ProductName, CategoryID, Price
FROM Products
WHERE (Price > 20 AND CategoryID = 4) OR CategoryID = 2;
```



### BETWEEN

## IN

### LIKE

### IS NULL / IS NOT NULL


