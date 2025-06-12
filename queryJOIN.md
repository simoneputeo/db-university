1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT *
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

```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```sql

```
