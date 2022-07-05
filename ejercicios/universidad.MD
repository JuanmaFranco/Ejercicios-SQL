# Ejercicios - Universidad

[![DER Universidad](/images/der/der-universidad.png)]()

## <span style="color:aqua">Consultas sobre una tabla</span>

1. Devuelve un listado con el primer apellido, segundo apellido y el nombre de todos los alumnos. El listado deberá estar ordenado alfabéticamente de menor a mayor por el primer apellido, segundo apellido y nombre.
    ```sql
    SELECT a.apellido1, a.apellido2, a.nombre
    FROM alumno a
    ORDER BY 1, 2, 3 ASC
    ```

2. Averigua el nombre y los dos apellidos de los alumnos que no han dado de alta su número de teléfono en la base de datos.
    ```sql
    SELECT a.nombre, a.apellido1, a.apellido2
    FROM alumno a
    WHERE a.telefono IS NULL
    ```

3. Devuelve el listado de los alumnos que nacieron en 1999.
    ```sql
    SELECT *
    FROM alumno a
    WHERE YEAR(a.fecha_nacimiento) = '1999'
    ```

4. Devuelve el listado de profesores que no han dado de alta su número de teléfono en la base de datos y además su nif termina en K.
    ```sql
    SELECT *
    FROM profesor p 
    WHERE p.telefono IS NULL AND p.nif LIKE '%K'
    ```

5. Devuelve el listado de las asignaturas que se imparten en el primer cuatrimestre, en el tercer curso del grado que tiene el identificador 7.
    ```sql
    SELECT *
    FROM asignatura a
    WHERE a.cuatrimestre = 1 AND a.curso = 3 AND a.id_grado = 7
    ```

## <span style="color:aqua">Consultas multitabla (Composición interna)<span>

1. Devuelve un listado con los datos de todas las alumnas que se han matriculado alguna vez en el Grado en Ingeniería Informática (Plan 2015).
    ```sql
    SELECT DISTINCT al.nombre, al.apellido1, al.apellido2
    FROM alumno al INNER JOIN alumno_se_matricula_asignatura asm ON al.id = asm.id_alumno
                   INNER JOIN asignatura asig ON asig.id = asm.id_asignatura
                   INNER JOIN grado g ON g.id = asig.id_grado
    WHERE g.nombre = 'Grado en Ingeniería Informática (Plan 2015)' AND al.sexo = 'M'
    ```

1. Devuelve un listado con todas las asignaturas ofertadas en el Grado en Ingeniería Informática (Plan 2015).
    ```sql

    ```

2. Devuelve un listado de los profesores junto con el nombre del departamento al que están vinculados. El listado debe devolver cuatro columnas, primer apellido, segundo apellido, nombre y nombre del departamento. El resultado estará ordenado alfabéticamente de menor a mayor por los apellidos y el nombre.
    ```sql

    ```

3. Devuelve un listado con el nombre de las asignaturas, año de inicio y año de fin del curso escolar del alumno con nif 26902806M.
    ```sql

    ```
    
4. Devuelve un listado con el nombre de todos los departamentos que tienen profesores que imparten alguna asignatura en el Grado en Ingeniería Informática (Plan 2015).
    ```sql

    ```

5. Devuelve un listado con todos los alumnos que se han matriculado en alguna asignatura durante el curso escolar 2018/2019.
    ```sql

    ```

## <span style="color:aqua">Consultas multitabla (Composición externa)<span>

1. Devuelve un listado con los nombres de todos los profesores y los departamentos que tienen vinculados. El listado también debe mostrar aquellos profesores que no tienen ningún departamento asociado. El listado debe devolver cuatro columnas, nombre del departamento, primer apellido, segundo apellido y nombre del profesor. El resultado estará ordenado alfabéticamente de menor a mayor por el nombre del departamento, apellidos y el nombre.
    ```sql

    ```

2. Devuelve un listado con los profesores que no están asociados a un departamento.
    ```sql

    ```

3. Devuelve un listado con los departamentos que no tienen profesores asociados.
    ```sql

    ```

4. Devuelve un listado con los profesores que no imparten ninguna asignatura.
    ```sql

    ```

5. Devuelve un listado con las asignaturas que no tienen un profesor asignado.
    ```sql

    ```

6. Devuelve un listado con todos los departamentos que tienen alguna asignatura que no se haya impartido en ningún curso escolar. El resultado debe mostrar el nombre del departamento y el nombre de la asignatura que no se haya impartido nunca.
    ```sql

    ```

## <span style="color:aqua">Consultas resúmen<span>

1. Devuelve el número total de alumnas que hay.
    ```sql

    ```

2. Calcula cuántos alumnos nacieron en 1999.
    ```sql

    ```

3. Calcula cuántos profesores hay en cada departamento. El resultado sólo debe mostrar dos columnas, una con el nombre del departamento y otra con el número de profesores que hay en ese departamento. El resultado sólo debe incluir los departamentos que tienen profesores asociados y deberá estar ordenado de mayor a menor por el número de profesores.
    ```sql

    ```

4. Devuelve un listado con todos los departamentos y el número de profesores que hay en cada uno de ellos. Tenga en cuenta que pueden existir departamentos que no tienen profesores asociados. Estos departamentos también tienen que aparecer en el listado.
    ```sql

    ```

5. Devuelve un listado con el nombre de todos los grados existentes en la base de datos y el número de asignaturas que tiene cada uno. Tenga en cuenta que pueden existir grados que no tienen asignaturas asociadas. Estos grados también tienen que aparecer en el listado. El resultado deberá estar ordenado de mayor a menor por el número de asignaturas.
    ```sql

    ```

6. Devuelve un listado con el nombre de todos los grados existentes en la base de datos y el número de asignaturas que tiene cada uno, de los grados que tengan más de 40 asignaturas asociadas.
    ```sql

    ```

7. Devuelve un listado que muestre el nombre de los grados y la suma del número total de créditos que hay para cada tipo de asignatura. El resultado debe tener tres columnas: nombre del grado, tipo de asignatura y la suma de los créditos de todas las asignaturas que hay de ese tipo. Ordene el resultado de mayor a menor por el número total de crédidos.
    ```sql

    ```

8. Devuelve un listado que muestre cuántos alumnos se han matriculado de alguna asignatura en cada uno de los cursos escolares. El resultado deberá mostrar dos columnas, una columna con el año de inicio del curso escolar y otra con el número de alumnos matriculados.
    ```sql

    ```

9. Devuelve un listado con el número de asignaturas que imparte cada profesor. El listado debe tener en cuenta aquellos profesores que no imparten ninguna asignatura. El resultado mostrará cinco columnas: id, nombre, primer apellido, segundo apellido y número de asignaturas. El resultado estará ordenado de mayor a menor por el número de asignaturas.
    ```sql

    ```

## <span style="color:aqua">Subconsultas<span>

1. Devuelve todos los datos del alumno más joven.
    ```sql

    ```

2. Devuelve un listado con los profesores que no están asociados a un departamento.
    ```sql

    ```

3. Devuelve un listado con los departamentos que no tienen profesores asociados.
    ```sql

    ```
    
4. Devuelve un listado con los profesores que tienen un departamento asociado y que no imparten ninguna asignatura.
    ```sql

    ```
5. Devuelve un listado con las asignaturas que no tienen un profesor asignado.
    ```sql

    ```
    
6. Devuelve un listado con todos los departamentos que no han impartido asignaturas en ningún curso escolar.
    ```sql

    ```