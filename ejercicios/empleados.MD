# Ejercicios - Gestión de Empleados

[![DER Gestión Empleados](/images/der/der-gestion-empleados.png)]()

## <span style="color:aqua">Consultas sobre una tabla</span>

1. Lista el primer apellido de todos los empleados.
    ```sql

    ```

2. Lista el primer apellido de los empleados eliminando los apellidos que estén repetidos.
    ```sql

    ```

3. Lista todas las columnas de la tabla empleado.
    ```sql

    ```

4. Lista el nombre y los apellidos de todos los empleados.
    ```sql

    ```

5. Lista el código de los departamentos de los empleados que aparecen en la tabla empleado.
    ```sql

    ```

6. Lista el código de los departamentos de los empleados que aparecen en la tabla empleado, eliminando los códigos que aparecen repetidos.
    ```sql

    ```

7. Lista el nombre y apellidos de los empleados en una única columna.
    ```sql

    ```

8. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en mayúscula.
    ```sql

    ```

9. Lista el nombre y apellidos de los empleados en una única columna, convirtiendo todos los caracteres en minúscula.
    ```sql

    ```

10. Lista el código de los empleados junto al nif, pero el nif deberá aparecer en dos columnas, una mostrará únicamente los dígitos del nif y la otra la letra.
    ```sql

    ```

11. Lista el nombre de cada departamento y el valor del presupuesto actual del que dispone. Para calcular este dato tendrá que restar al valor del presupuesto inicial (columna presupuesto) los gastos que se han generado (columna gastos). Tenga en cuenta que en algunos casos pueden existir valores negativos. Utilice un alias apropiado para la nueva columna columna que está calculando.
    ```sql

    ```

12. Lista el nombre de los departamentos y el valor del presupuesto actual ordenado de forma ascendente.
    ```sql

    ```

13. Lista el nombre de todos los departamentos ordenados de forma ascendente.
    ```sql

    ```

14. Lista el nombre de todos los departamentos ordenados de forma desscendente.
    ```sql

    ```

15. Lista los apellidos y el nombre de todos los empleados, ordenados de forma alfabética tendiendo en cuenta en primer lugar sus apellidos y luego su nombre.
    ```sql

    ```

16. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos que tienen mayor presupuesto.
    ```sql

    ```

17. Devuelve una lista con el nombre y el presupuesto, de los 3 departamentos que tienen menor presupuesto.
    ```sql

    ```

18. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que tienen mayor gasto.
    ```sql

    ```

19. Devuelve una lista con el nombre y el gasto, de los 2 departamentos que tienen menor gasto.
    ```sql

    ```

20. Devuelve una lista con 5 filas a partir de la tercera fila de la tabla empleado. La tercera fila se debe incluir en la respuesta. La respuesta debe incluir todas las columnas de la tabla empleado.
    ```sql

    ```

21. Devuelve una lista con el nombre de los departamentos y el presupuesto, de aquellos que tienen un presupuesto mayor o igual a 150000 euros.
    ```sql

    ```

22. Devuelve una lista con el nombre de los departamentos y el gasto, de aquellos que tienen menos de 5000 euros de gastos.
    ```sql

    ```

23. Devuelve una lista con el nombre de los departamentos y el presupesto, de aquellos que tienen un presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.
    ```sql

    ```

24. Devuelve una lista con el nombre de los departamentos que no tienen un presupuesto entre 100000 y 200000 euros. Sin utilizar el operador BETWEEN.
    ```sql

    ```

25. Devuelve una lista con el nombre de los departamentos que tienen un presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.
    ```sql

    ```

26. Devuelve una lista con el nombre de los departamentos que no tienen un presupuesto entre 100000 y 200000 euros. Utilizando el operador BETWEEN.
    ```sql

    ```

27. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de quellos departamentos donde los gastos sean mayores que el presupuesto del que disponen.
    ```sql

    ```

28. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de aquellos departamentos donde los gastos sean menores que el presupuesto del que disponen.
    ```sql

    ```

29. Devuelve una lista con el nombre de los departamentos, gastos y presupuesto, de aquellos departamentos donde los gastos sean iguales al presupuesto del que disponen.
    ```sql

    ```

30. Lista todos los datos de los empleados cuyo segundo apellido sea NULL.
    ```sql

    ```

31. Lista todos los datos de los empleados cuyo segundo apellido no sea NULL.
    ```sql

    ```

32. Lista todos los datos de los empleados cuyo segundo apellido sea López.
    ```sql

    ```

33. Lista todos los datos de los empleados cuyo segundo apellido sea Díaz o Moreno. Sin utilizar el operador IN.
    ```sql

    ```

34. Lista todos los datos de los empleados cuyo segundo apellido sea Díaz o Moreno. Utilizando el operador IN.
    ```sql

    ```

35. Lista los nombres, apellidos y nif de los empleados que trabajan en el departamento 3.
    ```sql

    ```

36. Lista los nombres, apellidos y nif de los empleados que trabajan en los departamentos 2, 4 o 5.
    ```sql

    ```

## <span style="color:aqua">Consultas multitabla (Composición interna)<span>

1. Devuelve un listado con los empleados y los datos de los departamentos donde trabaja cada uno.
    ```sql

    ```

2. Devuelve un listado con los empleados y los datos de los departamentos donde trabaja cada uno. Ordena el resultado, en primer lugar por el nombre del departamento (en orden alfabético) y en segundo lugar por los apellidos y el nombre de los empleados.
    ```sql

    ```

3. Devuelve un listado con el código y el nombre del departamento, solamente de aquellos departamentos que tienen empleados.
    ```sql

    ```
    
4. Devuelve un listado con el código, el nombre del departamento y el valor del presupuesto actual del que dispone, solamente de aquellos departamentos que tienen empleados. El valor del presupuesto actual lo puede calcular restando al valor del presupuesto inicial (columna presupuesto) el valor de los gastos que ha generado (columna gastos).
    ```sql

    ```

5. Devuelve el nombre del departamento donde trabaja el empleado que tiene el nif 38382980M.
    ```sql

    ```

6. Devuelve el nombre del departamento donde trabaja el empleado Pepe Ruiz Santana.
    ```sql

    ```

7. Devuelve un listado con los datos de los empleados que trabajan en el departamento de I+D. Ordena el resultado alfabéticamente.
    ```sql

    ```

8. Devuelve un listado con los datos de los empleados que trabajan en el departamento de Sistemas, Contabilidad o I+D. Ordena el resultado alfabéticamente.
    ```sql

    ```

9. Devuelve una lista con el nombre de los empleados que tienen los departamentos que no tienen un presupuesto entre 100000 y 200000 euros.
    ```sql

    ```

10. Devuelve un listado con el nombre de los departamentos donde existe algún empleado cuyo segundo apellido sea NULL. Tenga en cuenta que no debe mostrar nombres de departamentos que estén repetidos.
    ```sql

    ```

## <span style="color:aqua">Consultas multitabla (Composición externa)<span>

1. Devuelve un listado con todos los empleados junto con los datos de los departamentos donde trabajan. Este listado también debe incluir los empleados que no tienen ningún departamento asociado.
    ```sql

    ```

2. Devuelve un listado donde sólo aparezcan aquellos empleados que no tienen ningún departamento asociado.
    ```sql

    ```

3. Devuelve un listado donde sólo aparezcan aquellos departamentos que no tienen ningún empleado asociado.
    ```sql

    ```

4. Devuelve un listado con todos los empleados junto con los datos de los departamentos donde trabajan. El listado debe incluir los empleados que no tienen ningún departamento asociado y los departamentos que no tienen ningún empleado asociado. Ordene el listado alfabéticamente por el nombre del departamento.
    ```sql

    ```

5. Devuelve un listado con los empleados que no tienen ningún departamento asociado y los departamentos que no tienen ningún empleado asociado. Ordene el listado alfabéticamente por el nombre del departamento.
    ```sql

    ```

## <span style="color:aqua">Consultas resúmen<span>

1. Calcula la suma del presupuesto de todos los departamentos.
    ```sql

    ```

2. Calcula la media del presupuesto de todos los departamentos.
    ```sql

    ```

3. Calcula el valor mínimo del presupuesto de todos los departamentos.
    ```sql

    ```

4. Calcula el nombre del departamento y el presupuesto que tiene asignado, del departamento con menor presupuesto.
    ```sql

    ```

5. Calcula el valor máximo del presupuesto de todos los departamentos.
    ```sql

    ```

6. Calcula el nombre del departamento y el presupuesto que tiene asignado, del departamento con mayor presupuesto.
    ```sql

    ```

7. Calcula el número total de empleados que hay en la tabla empleado.
    ```sql

    ```

8. Calcula el número de empleados que no tienen NULL en su segundo apellido.
    ```sql

    ```

9. Calcula el número de empleados que hay en cada departamento. Tienes que devolver dos columnas, una con el nombre del departamento y otra con el número de empleados que tiene asignados.
    ```sql

    ```

10. Calcula el nombre de los departamentos que tienen más de 2 empleados. El resultado debe tener dos columnas, una con el nombre del departamento y otra con el número de empleados que tiene asignados.
    ```sql

    ```

11. Calcula el número de empleados que trabajan en cada uno de los departamentos. El resultado de esta consulta también tiene que incluir aquellos departamentos que no tienen ningún empleado asociado.
    ```sql

    ```

12. Calcula el número de empleados que trabajan en cada unos de los departamentos que tienen un presupuesto mayor a 200000 euros.
    ```sql

    ```

## <span style="color:aqua">Subconsultas<span>

### <span style="color:palegreen">Con operadores básicos de comparación</span>

1. Devuelve un listado con todos los empleados que tiene el departamento de Sistemas. (Sin utilizar INNER JOIN).
    ```sql

    ```

2. Devuelve el nombre del departamento con mayor presupuesto y la cantidad que tiene asignada.
    ```sql

    ```

3. Devuelve el nombre del departamento con menor presupuesto y la cantidad que tiene asignada.
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con ALL y ANY</span>

1. Devuelve el nombre del departamento con mayor presupuesto y la cantidad que tiene asignada. Sin hacer uso de MAX, ORDER BY ni LIMIT.
    ```sql

    ```

2. Devuelve el nombre del departamento con menor presupuesto y la cantidad que tiene asignada. Sin hacer uso de MIN, ORDER BY ni LIMIT.
    ```sql

    ```

3. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando ALL o ANY).
    ```sql

    ```

4. Devuelve los nombres de los departamentos que no tienen empleados asociados. (Utilizando ALL o ANY).
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con IN y NOT IN</span>

1. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando IN o NOT IN).
    ```sql

    ```

2. Devuelve los nombres de los departamentos que no tienen empleados asociados. (Utilizando IN o NOT IN).
    ```sql

    ```

### <span style="color:palegreen">Subconsultas con EXISTS y NOT EXISTS</span>

1. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando EXISTS o NOT EXISTS).
    ```sql

    ```

2. Devuelve los nombres de los departamentos que tienen empleados asociados. (Utilizando EXISTS o NOT EXISTS).
    ```sql

    ```