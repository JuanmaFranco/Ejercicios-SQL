# Ejercicios - Tienda informática

[![DER Tienda Informática](/images/der/der-tienda-informatica.png)]()

## <span style="color:aqua">Consultas sobre una tabla</span>

1. Lista el nombre de todos los productos que hay en la tabla producto.
   ```sql
   SELECT nombre FROM producto; 
   ```
   
2. Lista los nombres y los precios de todos los productos de la tabla producto.
   ```sql
   SELECT nombre, precio FROM producto;
   ```
   
3. Lista todas las columnas de la tabla producto.
    ```sql
    SELECT * FROM producto;
    ```

4. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD).
   ```sql
    SELECT nombre, precio * 249 AS 'Precio EUR', precio * 224 AS 'Precio USD' FROM producto
   ```

5. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD). Utiliza los siguientes alias para las columnas: nombre de producto, euros, dólares.
   ```sql
    SELECT nombre AS 'nombre de producto', precio * 249 AS 'euros', precio * 224 AS 'dólares' FROM producto
   ```

6. Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a mayúscula.
   ```sql

   ```

7. Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a minúscula.
   ```sql

   ```

8. Lista el nombre de todos los fabricantes en una columna, y en otra columna obtenga en mayúsculas los dos primeros caracteres del nombre del fabricante.
   ```sql

   ```

9.  Lista los nombres y los precios de todos los productos de la tabla producto, redondeando el valor del precio.
    ```sql

    ```

10. Lista los nombres y los precios de todos los productos de la tabla producto, truncando el valor del precio para mostrarlo sin ninguna cifra decimal.
    ```sql

    ```

11. Lista el código de los fabricantes que tienen productos en la tabla producto.
    ```sql

    ```

12. Lista el código de los fabricantes que tienen productos en la tabla producto, eliminando los códigos que aparecen repetidos.
    ```sql

    ```

13. Lista los nombres de los fabricantes ordenados de forma ascendente.
    ```sql

    ```

14. Lista los nombres de los fabricantes ordenados de forma descendente.
    ```sql

    ```

15. Lista los nombres de los productos ordenados en primer lugar por el nombre de forma ascendente y en segundo lugar por el precio de forma descendente.
    ```sql

    ```

16. Devuelve una lista con las 5 primeras filas de la tabla fabricante.
    ```sql

    ```

17. Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante. La cuarta fila también se debe incluir en la respuesta.
    ```sql

    ```

18. Lista el nombre y el precio del producto más barato. (Utilice solamente las cláusulas ORDER BY y LIMIT)
    ```sql

    ```

19. Lista el nombre y el precio del producto más caro. (Utilice solamente las cláusulas ORDER BY y LIMIT)
    ```sql

    ```

20. Lista el nombre de todos los productos del fabricante cuyo código de fabricante es igual a 2.
    ```sql

    ```

21. Lista el nombre de los productos que tienen un precio menor o igual a 120€.
    ```sql

    ```

22. Lista el nombre de los productos que tienen un precio mayor o igual a 400€.
    ```sql

    ```

23. Lista el nombre de los productos que no tienen un precio mayor o igual a 400€.
    ```sql

    ```

24. Lista todos los productos que tengan un precio entre 80€ y 300€. Sin utilizar el operador BETWEEN.
    ```sql

    ```

25. Lista todos los productos que tengan un precio entre 60€ y 200€. Utilizando el operador BETWEEN.
    ```sql

    ```
    
26. Lista todos los productos que tengan un precio mayor que 200€ y que el código de fabricante sea igual a 6.
    ```sql

    ```

27. Lista todos los productos donde el código de fabricante sea 1, 3 o 5. Sin utilizar el operador IN.
    ```sql

    ```

28. Lista todos los productos donde el código de fabricante sea 1, 3 o 5. Utilizando el operador IN.
    ```sql

    ```

29. Lista el nombre y el precio de los productos en céntimos (Habrá que multiplicar por 100 el valor del precio). Cree un alias para la columna que contiene el precio que se llame céntimos.
    ```sql

    ```

30. Lista los nombres de los fabricantes cuyo nombre empiece por la letra S.
    ```sql
    SELECT nombre FROM fabricante WHERE nombre LIKE "s%"
    ```

31. Lista los nombres de los fabricantes cuyo nombre termine por la vocal e.
    ```sql
    SELECT nombre FROM fabricante WHERE nombre LIKE "%e"
    ```

32. Lista los nombres de los fabricantes cuyo nombre contenga el carácter w.
    ```sql
    SELECT nombre FROM fabricante WHERE nombre LIKE "%w%"
    ```

33. Lista los nombres de los fabricantes cuyo nombre sea de 4 caracteres.
    ```sql
    SELECT nombre FROM fabricante WHERE LENGTH(nombre) = 4
    ```

34. Devuelve una lista con el nombre de todos los productos que contienen la cadena Portátil en el nombre.
    ```sql
    SELECT nombre FROM producto WHERE nombre LIKE "%Portátil%"
    ```

35. Devuelve una lista con el nombre de todos los productos que contienen la cadena Monitor en el nombre y tienen un precio inferior a 215 €.
    ```sql
    SELECT nombre FROM producto WHERE nombre LIKE "%Monitor%" AND precio < 215
    ```

36. Lista el nombre y el precio de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente).
    ```sql

    ```

## <span style="color:aqua">Consultas multitabla (Composición interna)<span>

1. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos.
    ```sql

    ```

2. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos. Ordene el resultado por el nombre del fabricante, por orden alfabético.
    ```sql

    ```

3. Devuelve una lista con el código del producto, nombre del producto, código del fabricante y nombre del fabricante, de todos los productos de la base de datos.
    ```sql

    ```

4. Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más barato.
    ```sql

    ```

5. Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más caro.
    ```sql

    ```

6. Devuelve una lista de todos los productos del fabricante Lenovo.
    ```sql

    ```

7. Devuelve una lista de todos los productos del fabricante Crucial que tengan un precio mayor que 200€.
    ```sql

    ```

8. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packardy Seagate. Sin utilizar el operador IN.
    ```sql

    ```

9. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packardy Seagate. Utilizando el operador IN.
    ```sql

    ```

10. Devuelve un listado con el nombre y el precio de todos los productos de los fabricantes cuyo nombre termine por la vocal e.
    ```sql

    ```

11. Devuelve un listado con el nombre y el precio de todos los productos cuyo nombre de fabricante contenga el carácter w en su nombre.
    ```sql

    ```

12. Devuelve un listado con el nombre de producto, precio y nombre de fabricante, de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente)
    ```sql

    ```

13. Devuelve un listado con el código y el nombre de fabricante, solamente de aquellos fabricantes que tienen productos asociados en la base de datos.
    ```sql

    ```

## <span style="color:aqua">Consultas multitabla (Composición externa)<span>

Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN.

1. Devuelva un listado de todos los fabricantes que existen en la base de datos, junto con los productos que tiene cada uno de ellos. El listado deberá mostrar también aquellos fabricantes que no tienen productos asociados.
    ```sql

    ```

2. Devuelva un listado donde sólo aparezcan aquellos fabricantes que no tienen ningún producto asociado.
    ```sql

    ```

## <span style="color:aqua">Consultas resúmen<span>

1. Calcula el número total de productos que hay en la tabla productos.
    ```sql

    ```

2. Calcula el número total de fabricantes que hay en la tabla fabricante.
    ```sql

    ```

3. Calcula el número de valores distintos de código de fabricante aparecen en la tabla productos.
    ```sql

    ```

4. Calcula la media del precio de todos los productos.
    ```sql

    ```
    
5. Calcula el precio más barato de todos los productos.
    ```sql

    ```

6. Calcula el precio más caro de todos los productos.
    ```sql

    ```

7. Lista el nombre y el precio del producto más barato.
    ```sql

    ```

8. Lista el nombre y el precio del producto más caro.
    ```sql

    ```

9. Calcula la suma de los precios de todos los productos.
    ```sql

    ```

10. Calcula el número de productos que tiene el fabricante Asus.
    ```sql

    ```

11. Calcula la media del precio de todos los productos del fabricante Asus.
    ```sql

    ```

12. Calcula el precio más barato de todos los productos del fabricante Asus.
    ```sql

    ```

13. Calcula el precio más caro de todos los productos del fabricante Asus.
    ```sql

    ```

14. Calcula la suma de todos los productos del fabricante Asus.
    ```sql

    ```

15. Muestra el precio máximo, precio mínimo, precio medio y el número total de productos que tiene el fabricante Crucial.
    ```sql

    ```

16. Muestra el número total de productos que tiene cada uno de los fabricantes. El listado también debe incluir los fabricantes que no tienen ningún producto. El resultado mostrará dos columnas, una con el nombre del fabricante y otra con el número de productos que tiene. Ordene el resultado descendentemente por el número de productos.
    ```sql

    ```

17. Muestra el precio máximo, precio mínimo y precio medio de los productos de cada uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los datos que se solicitan.
    ```sql

    ```

18. Muestra el precio máximo, precio mínimo, precio medio y el número total de productos de los fabricantes que tienen un precio medio superior a 200€. No es necesario mostrar el nombre del fabricante, con el código del fabricante es suficiente.
    ```sql

    ```

19. Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo, precio medio y el número total de productos de los fabricantes que tienen un precio medio superior a 200€. Es necesario mostrar el nombre del fabricante.
    ```sql

    ```

20. Calcula el número de productos que tienen un precio mayor o igual a 180€.
    ```sql

    ```

21. Calcula el número de productos que tiene cada fabricante con un precio mayor o igual a 180€.
    ```sql

    ```

22. Lista el precio medio los productos de cada fabricante, mostrando solamente el código del fabricante.
    ```sql

    ```

23. Lista el precio medio los productos de cada fabricante, mostrando solamente el nombre del fabricante.
    ```sql

    ```

24. Lista los nombres de los fabricantes cuyos productos tienen un precio medio mayor o igual a 150€.
    ```sql

    ```

25. Devuelve un listado con los nombres de los fabricantes que tienen 2 o más productos.
    ```sql

    ```

26. Devuelve un listado con los nombres de los fabricantes y el número de productos que tiene cada uno con un precio superior o igual a 220 €. No es necesario mostrar el nombre de los fabricantes que no tienen productos que cumplan la condición.
    ```sql

    ```

27. Devuelve un listado con los nombres de los fabricantes y el número de productos que tiene cada uno con un precio superior o igual a 220 €. El listado debe mostrar el nombre de todos los fabricantes, es decir, si hay algún fabricante que no tiene productos con un precio superior o igual a 220€ deberá aparecer en el listado con un valor igual a 0 en el número de productos.
    ```sql

    ```

28. Devuelve un listado con los nombres de los fabricantes donde la suma del precio de todos sus productos es superior a 1000 €.
    ```sql

    ```

29. Devuelve un listado con el nombre del producto más caro que tiene cada fabricante. El resultado debe tener tres columnas: nombre del producto, precio y nombre del fabricante. El resultado tiene que estar ordenado alfabéticamente de menor a mayor por el nombre del fabricante.
    ```sql

    ```

## <span style="color:aqua">Subconsultas<span>

### <span style="color:palegreen">Con operadores básicos de comparación</span>

1. Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER JOIN).
    ```sql

    ```

2. Devuelve todos los datos de los productos que tienen el mismo precio que el producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).
    ```sql

    ```

3. Lista el nombre del producto más caro del fabricante Lenovo.
    ```sql

    ```

4. Lista el nombre del producto más barato del fabricante Hewlett-Packard.
    ```sql

    ```

5. Devuelve todos los productos de la base de datos que tienen un precio mayor o igual al producto más caro del fabricante Lenovo.
    ```sql

    ```

6. Lista todos los productos del fabricante Asus que tienen un precio superior al precio medio de todos sus productos.
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con ALL y ANY</span>

1. Devuelve el producto más caro que existe en la tabla producto sin hacer uso de MAX, ORDER BY ni LIMIT.
    ```sql

    ```

2. Devuelve el producto más barato que existe en la tabla producto sin hacer uso de MIN, ORDER BY ni LIMIT.
    ```sql

    ```

3. Devuelve los nombres de los fabricantes que tienen productos asociados. (Utilizando ALL o ANY).
    ```sql

    ```

4. Devuelve los nombres de los fabricantes que no tienen productos asociados. (Utilizando ALL o ANY).
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con IN y NOT IN</span>

1. Devuelve los nombres de los fabricantes que tienen productos asociados. (Utilizando IN o NOT IN).
    ```sql

    ```

2. Devuelve los nombres de los fabricantes que no tienen productos asociados. (Utilizando IN o NOT IN).
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con EXISTS y NOT EXISTS</span>

1. Devuelve los nombres de los fabricantes que tienen productos asociados. (Utilizando EXISTS o NOT EXISTS).
    ```sql

    ```
    
2. Devuelve los nombres de los fabricantes que no tienen productos asociados. (Utilizando EXISTS o NOT EXISTS).
    ```sql

    ```

### <span style="color:palegreen">Subconsultas correlacionadas</span>

1. Lista el nombre de cada fabricante con el nombre y el precio de su producto más caro.
    ```sql

    ```

2. Devuelve un listado de todos los productos que tienen un precio mayor o igual a la media de todos los productos de su mismo fabricante.
    ```sql

    ```

3. Lista el nombre del producto más caro del fabricante Lenovo.
    ```sql

    ```

### <span style="color:palegreen">Subconsultas (En la cláusula HAVING)</span>

1. Devuelve un listado con todos los nombres de los fabricantes que tienen el mismo número de productos que el fabricante Lenovo.
    ```sql

    ```