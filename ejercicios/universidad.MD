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
    SELECT a.nombre
    FROM asignatura a INNER JOIN grado g ON a.id_grado = g.id
    WHERE g.nombre = 'Grado en Ingeniería Informática (Plan 2015)'
    ```

2. Devuelve un listado de los profesores junto con el nombre del departamento al que están vinculados. El listado debe devolver cuatro columnas, primer apellido, segundo apellido, nombre y nombre del departamento. El resultado estará ordenado alfabéticamente de menor a mayor por los apellidos y el nombre.
    ```sql
    SELECT p.apellido1, p.apellido2, p.nombre, d.nombre
    FROM profesor p INNER JOIN departamento d ON p.id_departamento = d.id
    ORDER BY 1, 2, 3 ASC
    ```

3. Devuelve un listado con el nombre de las asignaturas, año de inicio y año de fin del curso escolar del alumno con nif 26902806M.
    ```sql
    SELECT a.nombre, ce.anyo_inicio, ce.anyo_fin
    FROM asignatura a INNER JOIN alumno_se_matricula_asignatura asm ON a.id = asm.id_asignatura
                      INNER JOIN curso_escolar ce ON asm.id_curso_escolar = ce.id
                      INNER JOIN alumno al ON al.id = asm.id_alumno
    WHERE al.nif = '26902806M'
    ```
    
4. Devuelve un listado con el nombre de todos los departamentos que tienen profesores que imparten alguna asignatura en el Grado en Ingeniería Informática (Plan 2015).
    ```sql
    SELECT DISTINCT d.nombre
    FROM departamento d INNER JOIN profesor p ON d.id = p.id_departamento
                        INNER JOIN asignatura a ON p.id = a.id_profesor
                        INNER JOIN grado g ON g.id = a.id_grado
    WHERE g.nombre = 'Grado en Ingeniería Informática (Plan 2015)'
    ```

5. Devuelve un listado con todos los alumnos que se han matriculado en alguna asignatura durante el curso escolar 2018/2019.
    ```sql
    SELECT *
    FROM alumno al INNER JOIN alumno_se_matricula_asignatura asm ON al.id = asm.id_alumno
                   INNER JOIN asignatura a ON asm.id_asignatura = a.id
                   INNER JOIN curso_escolar ce ON ce.id = asm.id_curso_escolar
    WHERE ce.anyo_inicio = '2018' AND ce.anyo_fin = '2019'
    ```

## <span style="color:aqua">Consultas multitabla (Composición externa)<span>

1. Devuelve un listado con los nombres de todos los profesores y los departamentos que tienen vinculados. El listado también debe mostrar aquellos profesores que no tienen ningún departamento asociado. El listado debe devolver cuatro columnas, nombre del departamento, primer apellido, segundo apellido y nombre del profesor. El resultado estará ordenado alfabéticamente de menor a mayor por el nombre del departamento, apellidos y el nombre.
    ```sql
    SELECT d.nombre, p.apellido1, p.apellido2, p.nombre
    FROM profesor p LEFT JOIN departamento d ON p.id_departamento = d.id
    ORDER BY 1, 2, 3, 4 ASC
    ```

2. Devuelve un listado con los profesores que no están asociados a un departamento.
    ```sql
    SELECT d.nombre, p.apellido1, p.apellido2, p.nombre
    FROM profesor p LEFT JOIN departamento d ON p.id_departamento = d.id
    WHERE p.id_departamento IS NULL
    ```

3. Devuelve un listado con los departamentos que no tienen profesores asociados.
    ```sql
    SELECT d.nombre
    FROM profesor p RIGHT JOIN departamento d ON p.id_departamento = d.id
    WHERE p.id_departamento IS NULL
    ```

4. Devuelve un listado con los profesores que no imparten ninguna asignatura.
    ```sql
    SELECT p.nombre, p.apellido1, p.apellido2
    FROM profesor p LEFT JOIN asignatura a ON a.id_profesor = p.id
    WHERE a.id_profesor IS NULL
    ```

5. Devuelve un listado con las asignaturas que no tienen un profesor asignado.
    ```sql
    SELECT a.nombre
    FROM profesor p RIGHT JOIN asignatura a ON a.id_profesor = p.id
    WHERE a.id_profesor IS NULL
    ```

6. Devuelve un listado con todos los departamentos que tienen alguna asignatura que no se haya impartido en ningún curso escolar. El resultado debe mostrar el nombre del departamento y el nombre de la asignatura que no se haya impartido nunca.
    ```sql
    SELECT d.nombre as 'Departamento', a.nombre as 'Asignatura'
    FROM ((departamento d INNER JOIN profesor p ON d.id = p.id_departamento)
                          INNER JOIN asignatura a ON p.id = a.id_profesor)
                          LEFT JOIN alumno_se_matricula_asignatura asm ON a.id = asm.id_asignatura
    WHERE asm.id_curso_escolar IS NULL
    ```

## <span style="color:aqua">Consultas resúmen<span>

1. Devuelve el número total de alumnas que hay.
    ```sql
    SELECT COUNT(a.id)
    FROM alumno a
    WHERE a.sexo = 'M'
    ```

2. Calcula cuántos alumnos nacieron en 1999.
    ```sql
    SELECT COUNT(*)
    FROM alumno a
    WHERE YEAR(a.fecha_nacimiento) = '1999'
    ```

3. Calcula cuántos profesores hay en cada departamento. El resultado sólo debe mostrar dos columnas, una con el nombre del departamento y otra con el número de profesores que hay en ese departamento. El resultado sólo debe incluir los departamentos que tienen profesores asociados y deberá estar ordenado de mayor a menor por el número de profesores.
    ```sql
    SELECT d.nombre, COUNT(*) AS 'Cantidad de profesores'
    FROM departamento d INNER JOIN profesor p ON p.id_departamento = d.id
    GROUP BY d.nombre
    ORDER BY 2 DESC
    ```

4. Devuelve un listado con todos los departamentos y el número de profesores que hay en cada uno de ellos. Tenga en cuenta que pueden existir departamentos que no tienen profesores asociados. Estos departamentos también tienen que aparecer en el listado.
    ```sql
    SELECT d.nombre, COUNT(p.id_departamento) AS 'Cantidad de profesores'
    FROM departamento d LEFT JOIN profesor p ON p.id_departamento = d.id
    GROUP BY d.nombre
    ORDER BY 2 DESC
    ```

5. Devuelve un listado con el nombre de todos los grados existentes en la base de datos y el número de asignaturas que tiene cada uno. Tenga en cuenta que pueden existir grados que no tienen asignaturas asociadas. Estos grados también tienen que aparecer en el listado. El resultado deberá estar ordenado de mayor a menor por el número de asignaturas.
    ```sql
    SELECT g.nombre, COUNT(a.id) AS 'Cantidad de Asignaturas'
    FROM grado g INNER JOIN asignatura a ON g.id = a.id_grado
    GROUP BY g.nombre
    ORDER BY 2 DESC
    ```

6. Devuelve un listado con el nombre de todos los grados existentes en la base de datos y el número de asignaturas que tiene cada uno, de los grados que tengan más de 40 asignaturas asociadas.
    ```sql
    SELECT g.nombre, COUNT(a.id) AS 'Cantidad de asignaturas'
    FROM grado g INNER JOIN asignatura a ON g.id = a.id_grado
    GROUP BY g.nombre
    HAVING COUNT(a.id) > 40
    ```

7. Devuelve un listado que muestre el nombre de los grados y la suma del número total de créditos que hay para cada tipo de asignatura. El resultado debe tener tres columnas: nombre del grado, tipo de asignatura y la suma de los créditos de todas las asignaturas que hay de ese tipo. Ordene el resultado de mayor a menor por el número total de crédidos.
    ```sql
    SELECT g.nombre, a.tipo, SUM(a.creditos) AS 'Cantidad de créditos'
    FROM grado g INNER JOIN asignatura a ON g.id = a.id_grado
    GROUP BY a.tipo, g.nombre
    ORDER BY 3 DESC
    ```

8. Devuelve un listado que muestre cuántos alumnos se han matriculado de alguna asignatura en cada uno de los cursos escolares. El resultado deberá mostrar dos columnas, una columna con el año de inicio del curso escolar y otra con el número de alumnos matriculados.
    ```sql
    SELECT ce.anyo_inicio, COUNT(DISTINCT asm.id_alumno)
    FROM alumno a INNER JOIN alumno_se_matricula_asignatura asm ON a.id = asm.id_alumno
                  INNER JOIN asignatura asig ON asig.id = asm.id_asignatura
                  INNER JOIN curso_escolar ce ON ce.id = asm.id_curso_escolar
    GROUP BY ce.anyo_inicio
    ```

9. Devuelve un listado con el número de asignaturas que imparte cada profesor. El listado debe tener en cuenta aquellos profesores que no imparten ninguna asignatura. El resultado mostrará cinco columnas: id, nombre, primer apellido, segundo apellido y número de asignaturas. El resultado estará ordenado de mayor a menor por el número de asignaturas.
    ```sql
    SELECT p.id, p.nombre, p.apellido1, p.apellido2, COUNT(a.id_profesor)
    FROM asignatura a RIGHT JOIN profesor p ON a.id_profesor = p.id
    GROUP BY p.id
    ORDER BY 5 DESC
    ```

## <span style="color:aqua">Subconsultas<span>

1. Devuelve todos los datos del alumno más joven.
    ```sql
    SELECT *
    FROM alumno a 
    WHERE a.fecha_nacimiento = (SELECT MAX(a.fecha_nacimiento)
                                FROM alumno a)
    ```

2. Devuelve un listado con los profesores que no están asociados a un departamento.
    ```sql
    SELECT p.nombre, p.apellido1, p.apellido2
    FROM profesor p 
    WHERE p.id_departamento NOT IN (SELECT d.id
                                    FROM departamento d)
    ```

3. Devuelve un listado con los departamentos que no tienen profesores asociados.
    ```sql
    SELECT d.nombre
    FROM departamento d 
    WHERE d.id NOT IN (SELECT DISTINCT p.id_departamento 
                       FROM profesor p)
    ```
    
4. Devuelve un listado con los profesores que tienen un departamento asociado y que no imparten ninguna asignatura.
    ```sql
    SELECT p.nombre, p.apellido1, p.apellido2
    FROM profesor p 
    WHERE p.id_departamento IN (SELECT d.id
                                FROM departamento d)
            AND NOT EXISTS (SELECT DISTINCT a.id_profesor
                            FROM asignatura a
                            WHERE a.id_profesor = p.id)
    ```
5. Devuelve un listado con las asignaturas que no tienen un profesor asignado.
    ```sql
    SELECT a.nombre
    FROM asignatura a 
    WHERE NOT EXISTS (SELECT p.id 
                      FROM profesor p
                      WHERE p.id = a.id_profesor)
    ```
    
6. Devuelve un listado con todos los departamentos que no han impartido asignaturas en ningún curso escolar.
    ```sql
    SELECT * 
    FROM departamento 
    WHERE id NOT IN 
        (SELECT id_departamento 
        FROM profesor p 
        WHERE EXISTS (SELECT id_profesor 
                      FROM asignatura a
                      WHERE p.id = a.id_profesor 
                            AND NOT EXISTS (SELECT id_asignatura 
                                            FROM alumno_se_matricula_asignatura asm
                                            WHERE a.id = asm.id_asignatura) 
                     ) 
        )
    ```