# Ejercicios - Gestión de Ventas

[![DER Gestión Ventas](/images/der/der-gestion-ventas.png)]()

## <span style="color:aqua">Consultas sobre una tabla</span>

1. Devuelve un listado con todos los pedidos que se han realizado. Los pedidos deben estar ordenados por la fecha de realización, mostrando en primer lugar los pedidos más recientes.
    ```sql
    SELECT * 
    FROM pedido
    ORDER BY fecha DESC
    ```

2. Devuelve todos los datos de los dos pedidos de mayor valor.
    ```sql
    SELECT * 
    FROM pedido
    ORDER BY total DESC
    LIMIT 2
    ```

3. Devuelve un listado con los identificadores de los clientes que han realizado algún pedido. Tenga en cuenta que no debe mostrar identificadores que estén repetidos.
    ```sql
    SELECT DISTINCT p.id_cliente
    FROM pedido p
    ```

4. Devuelve un listado de todos los pedidos que se realizaron durante el año 2017, cuya cantidad total sea superior a 500€.
    ```sql
    SELECT * 
    FROM pedido p
    WHERE YEAR(p.fecha) = 2017 AND p.total > 500
    ```

5. Devuelve un listado con el nombre y los apellidos de los comerciales que tienen una comisión entre 0.05 y 0.11.
    ```sql
    SELECT c.nombre, c.apellido1, c.apellido2
    FROM comercial c
    WHERE c.`comisión` BETWEEN 0.05 AND 0.11
    ```

6. Devuelve el valor de la comisión de mayor valor que existe en la tabla comercial.
    ```sql
    SELECT MAX(c.`comisión`) AS 'Máxima comisión'
    FROM comercial c
    ```

7. Devuelve el identificador, nombre y primer apellido de aquellos clientes cuyo segundo apellido no es NULL. El listado deberá estar ordenado alfabéticamente por apellidos y nombre.
    ```sql
    SELECT c.id, c.nombre, c.apellido1
    FROM cliente c
    WHERE c.apellido2 IS NOT NULL 
    ORDER BY 3 ASC, 2 ASC
    ```

8. Devuelve un listado de los nombres de los clientes que empiezan por A y terminan por n y también los nombres que empiezan por P. El listado deberá estar ordenado alfabéticamente.
    ```sql
    SELECT c.nombre
    FROM cliente c
    WHERE c.nombre LIKE 'a%' AND c.nombre LIKE '%n' OR c.nombre LIKE 'p%'
    ORDER BY 1 ASC 
    ```

9. Devuelve un listado de los nombres de los clientes que no empiezan por A. El listado deberá estar ordenado alfabéticamente.
    ```sql
    SELECT c.nombre
    FROM cliente c
    WHERE c.nombre NOT LIKE 'a%'
    ORDER BY 1 ASC 
    ```

10. Devuelve un listado con los nombres de los comerciales que terminan por 'el' u 'o'. Tenga en cuenta que se deberán eliminar los nombres repetidos.
    ```sql
    SELECT DISTINCT c.nombre
    FROM comercial c
    WHERE c.nombre LIKE '%el' OR c.nombre LIKE '%o'
    ```

## <span style="color:aqua">Consultas multitabla (Composición interna)<span>

1. Devuelve un listado con el identificador, nombre y los apellidos de todos los clientes que han realizado algún pedido. El listado debe estar ordenado alfabéticamente y se deben eliminar los elementos repetidos.
    ```sql
    SELECT DISTINCT c.id, c.nombre, c.apellido1, c.apellido2
    FROM cliente c INNER JOIN pedido p ON c.id = p.id_cliente
    ORDER BY 3 ASC, 4 ASC, 2 ASC
    ```

2. Devuelve un listado que muestre todos los pedidos que ha realizado cada cliente. El resultado debe mostrar todos los datos de los pedidos y del cliente. El listado debe mostrar los datos de los clientes ordenados alfabéticamente.
    ```sql
    SELECT c.id, c.nombre, c.apellido1, c.apellido2, p.id, p.fecha, p.total
    FROM cliente c INNER JOIN pedido p ON c.id = p.id_cliente
    ORDER BY 3 ASC, 4 ASC, 2 ASC
    ```

3. Devuelve un listado que muestre todos los pedidos en los que ha participado un comercial. El resultado debe mostrar todos los datos de los pedidos y de los comerciales. El listado debe mostrar los datos de los comerciales ordenados alfabéticamente.
    ```sql
    SELECT co.nombre, co.apellido1, co.apellido2, p.id, p.fecha, p.total
    FROM comercial co INNER JOIN pedido p ON co.id = p.id_cliente
    ORDER BY 2 ASC, 3 ASC, 1 ASC
    ```

4. Devuelve un listado que muestre todos los clientes, con todos los pedidos que han realizado y con los datos de los comerciales asociados a cada pedido.
    ```sql
    SELECT *
    FROM cliente c INNER JOIN pedido p ON c.id = p.id_cliente 
                   INNER JOIN comercial co ON p.id_comercial = co.id
    ```

5. Devuelve un listado de todos los clientes que realizaron un pedido durante el año 2017, cuya cantidad esté entre 300 € y 1000 €.
    ```sql
    SELECT *
    FROM cliente c INNER JOIN pedido p ON c.id = p.id_cliente
    WHERE YEAR(p.fecha) = 2017 AND p.total BETWEEN 300 AND 1000
    ```

6. Devuelve el nombre y los apellidos de todos los comerciales que ha participado en algún pedido realizado por María Santana Moreno.
    ```sql
    SELECT DISTINCT co.nombre, co.apellido1, co.apellido2
    FROM comercial co INNER JOIN pedido p ON co.id = p.id_comercial
                      INNER JOIN cliente c ON p.id_cliente = c.id
    WHERE c.nombre = 'María' AND c.apellido1 = 'Santana' AND c.apellido2 = 'Moreno'
    ```

7. Devuelve el nombre de todos los clientes que han realizado algún pedido con el comercial Daniel Sáez Vega.
    ```sql
    SELECT DISTINCT c.nombre, c.apellido1, c.apellido2
    FROM comercial co INNER JOIN pedido p ON co.id = p.id_comercial
                      INNER JOIN cliente c ON p.id_cliente = c.id
    WHERE co.nombre = 'Daniel' AND co.apellido1 = 'Sáez' AND co.apellido2 = 'Vega'
    ```

## <span style="color:aqua">Consultas multitabla (Composición externa)<span>

1. Devuelve un listado con todos los clientes junto con los datos de los pedidos que han realizado. Este listado también debe incluir los clientes que no han realizado ningún pedido. El listado debe estar ordenado alfabéticamente por el primer apellido, segundo apellido y nombre de los clientes.
    ```sql
    SELECT *
    FROM cliente c LEFT JOIN pedido p ON c.id = p.id_cliente
    ORDER BY c.apellido1 ASC, c.apellido2 ASC, c.nombre ASC 
    ```

2. Devuelve un listado con todos los comerciales junto con los datos de los pedidos que han realizado. Este listado también debe incluir los comerciales que no han realizado ningún pedido. El listado debe estar ordenado alfabéticamente por el primer apellido, segundo apellido y nombre de los comerciales.
    ```sql
    SELECT *
    FROM comercial c LEFT JOIN pedido p ON c.id = p.id_cliente
    ORDER BY c.apellido1 ASC, c.apellido2 ASC, c.nombre ASC 
    ```

3. Devuelve un listado que solamente muestre los clientes que no han realizado ningún pedido.
    ```sql
    SELECT *
    FROM cliente c LEFT JOIN pedido p ON c.id = p.id_cliente
    WHERE p.id_cliente IS NULL
    ORDER BY c.apellido1 ASC, c.apellido2 ASC, c.nombre ASC 
    ```

4. Devuelve un listado que solamente muestre los comerciales que no han realizado ningún pedido.
    ```sql
    SELECT *
    FROM comercial c LEFT JOIN pedido p ON c.id = p.id_comercial
    WHERE p.id_comercial IS NULL
    ORDER BY c.apellido1 ASC, c.apellido2 ASC, c.nombre ASC
    ```

5. Devuelve un listado con los clientes que no han realizado ningún pedido y de los comerciales que no han participado en ningún pedido. Ordene el listado alfabéticamente por los apellidos y el nombre. En en listado deberá diferenciar de algún modo los clientes y los comerciales.
    ```sql

    ```

6. ¿Se podrían realizar las consultas anteriores con NATURAL LEFT JOIN o NATURAL RIGHT JOIN? Justifique su respuesta.
    ```sql

    ```

## <span style="color:aqua">Consultas resúmen<span>

1. Calcula la cantidad total que suman todos los pedidos que aparecen en la tabla pedido.
    ```sql
    SELECT SUM(p.total) AS 'Total'
    FROM pedido p
    ```

2. Calcula la cantidad media de todos los pedidos que aparecen en la tabla pedido.
    ```sql
    SELECT AVG(p.total) AS 'Promedio'
    FROM pedido p
    ```

3. Calcula el número total de comerciales distintos que aparecen en la tabla pedido.
    ```sql
    SELECT COUNT(DISTINCT p.id_comercial) AS 'Comerciales distintos'
    FROM pedido p 
    ```

4. Calcula el número total de clientes que aparecen en la tabla cliente.
    ```sql
    SELECT COUNT(*) AS 'Cantidad de Clientes'
    FROM cliente c
    ```

5. Calcula cuál es la mayor cantidad que aparece en la tabla pedido.
    ```sql
    SELECT MAX(p.total) AS 'Mayor cantidad'
    FROM pedido p
    ```

6. Calcula cuál es la menor cantidad que aparece en la tabla pedido.
    ```sql
    SELECT MIN(p.total) AS 'Menor cantidad'
    FROM pedido p
    ```
    
7. Calcula cuál es el valor máximo de categoría para cada una de las ciudades que aparece en la tabla cliente.
    ```sql
    SELECT c.ciudad, MAX(c.`categoría`) AS 'Valor máximo'
    FROM cliente c
    GROUP BY c.ciudad
    ```

8. Calcula cuál es el máximo valor de los pedidos realizados durante el mismo día para cada uno de los clientes. Es decir, el mismo cliente puede haber realizado varios pedidos de diferentes cantidades el mismo día. Se pide que se calcule cuál es el pedido de máximo valor para cada uno de los días en los que un cliente ha realizado un pedido. Muestra el identificador del cliente, nombre, apellidos, la fecha y el valor de la cantidad.
    ```sql

    ```

9. Calcula cuál es el máximo valor de los pedidos realizados durante el mismo día para cada uno de los clientes, teniendo en cuenta que sólo queremos mostrar aquellos pedidos que superen la cantidad de 2000 €.
    ```sql

    ```

10. Calcula el máximo valor de los pedidos realizados para cada uno de los comerciales durante la fecha 2016-08-17. Muestra el identificador del comercial, nombre, apellidos y total.
    ```sql

    ```

11. Devuelve un listado con el identificador de cliente, nombre y apellidos y el número total de pedidos que ha realizado cada uno de clientes. Tenga en cuenta que pueden existir clientes que no han realizado ningún pedido. Estos clientes también deben aparecer en el listado indicando que el número de pedidos realizados es 0.
    ```sql

    ```

12. Devuelve un listado con el identificador de cliente, nombre y apellidos y el número total de pedidos que ha realizado cada uno de clientes durante el año 2017.
    ```sql

    ```

13. Devuelve un listado que muestre el identificador de cliente, nombre, primer apellido y el valor de la máxima cantidad del pedido realizado por cada uno de los clientes. El resultado debe mostrar aquellos clientes que no han realizado ningún pedido indicando que la máxima cantidad de sus pedidos realizados es 0. Puede hacer uso de la función IFNULL.
    ```sql

    ```

14. Devuelve cuál ha sido el pedido de máximo valor que se ha realizado cada año.
    ```sql

    ```

15. Devuelve el número total de pedidos que se han realizado cada año.
    ```sql

    ```

## <span style="color:aqua">Subconsultas<span>

### <span style="color:palegreen">Con operadores básicos de comparación</span>

1. Devuelve un listado con todos los pedidos que ha realizado Adela Salas Díaz. (Sin utilizar INNER JOIN).
    ```sql

    ```

2. Devuelve el número de pedidos en los que ha participado el comercial Daniel Sáez Vega. (Sin utilizar INNER JOIN)
    ```sql

    ```

3. Devuelve los datos del cliente que realizó el pedido más caro en el año 2019. (Sin utilizar INNER JOIN)
    ```sql

    ```

4. Devuelve la fecha y la cantidad del pedido de menor valor realizado por el cliente Pepe Ruiz Santana.
    ```sql

    ```

5. Devuelve un listado con los datos de los clientes y los pedidos, de todos los clientes que han realizado un pedido durante el año 2017 con un valor mayor o igual al valor medio de los pedidos realizados durante ese mismo año.
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con ALL y ANY</span>

1. Devuelve el pedido más caro que existe en la tabla pedido si hacer uso de MAX, ORDER BY ni LIMIT.
    ```sql

    ```

2. Devuelve un listado de los clientes que no han realizado ningún pedido. (Utilizando ANY o ALL).
    ```sql

    ```

3. Devuelve un listado de los comerciales que no han realizado ningún pedido. (Utilizando ANY o ALL).
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con IN y NOT IN</span>

1. Devuelve un listado de los clientes que no han realizado ningún pedido. (Utilizando IN o NOT IN).
    ```sql

    ```

2. Devuelve un listado de los comerciales que no han realizado ningún pedido. (Utilizando IN o NOT IN).
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con EXISTS y NOT EXISTS</span>

1. Devuelve un listado de los clientes que no han realizado ningún pedido. (Utilizando EXISTS o NOT EXISTS).
    ```sql

    ```
    
2. Devuelve un listado de los comerciales que no han realizado ningún pedido. (Utilizando EXISTS o NOT EXISTS).
    ```sql

    ```