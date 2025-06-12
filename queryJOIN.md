1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT
`students`.`name`, `students`.`surname`,
`students`.`date_of_birth`, `students`.`fiscal_code`,
`students`.`enrolment_date`, `students`.`registration_number`,
`students`.`email`
FROM  uni.students
INNER JOIN uni.degrees
ON uni.students.degree_id = uni.degrees.id
WHERE uni.degrees.name = "Corso di Laurea in Economia";
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql
SELECT *
FROM uni.degrees
INNER JOIN uni.departments
ON uni.degrees.department_id = uni.departments.id
WHERE uni.degrees.level = "magistrale"
AND uni.departments.name = "Dipartimento di Neuroscienze";
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT *
FROM uni.course_teacher
INNER JOIN uni.courses
ON uni.course_teacher.course_id = uni.courses.id
INNER JOIN uni.teachers
ON uni.course_teacher.teacher_id = uni.teachers.id
WHERE uni.teachers.id = 44;
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT *
FROM uni.students
INNER JOIN uni.degrees
ON uni.students.degree_id = uni.degrees.id
INNER JOIN uni.departments
ON uni.degrees.department_id = uni.departments.id
ORDER BY uni.students.surname, uni.students.name;
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT
uni.degrees.id AS degree_id,
uni.degrees.name AS degree_name,
uni.degrees.level,
uni.degrees.address,
uni.degrees.email,
uni.degrees.website,
uni.degrees.level,
uni.courses.name AS course_name,
uni.courses.year,
uni.courses.period,
uni.teachers.surname,
uni.teachers.name
FROM uni.degrees
INNER JOIN uni.courses
ON uni.degrees.id = uni.courses.degree_id
INNER JOIN uni.course_teacher
ON uni.courses.id = uni.course_teacher.course_id
INNER JOIN uni.teachers
ON uni.course_teacher.teacher_id = uni.teachers.id
ORDER BY uni.degrees.name, uni.courses.year, uni.courses.period;
```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql
SELECT DISTINCT uni.teachers.id, uni.teachers.name, uni.teachers.surname
FROM uni.teachers
INNER JOIN uni.course_teacher
ON uni.teachers.id = uni.course_teacher.teacher_id
INNER JOIN uni.courses
ON uni.course_teacher.course_id = uni.courses.id
INNER JOIN uni.degrees
ON uni.courses.degree_id = uni.degrees.id
INNER JOIN uni.departments
ON uni.degrees.department_id = uni.departments.id
WHERE uni.departments.name = 'Dipartimento di Matematica'
ORDER BY uni.teachers.surname;

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```sql

```
