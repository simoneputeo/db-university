1. Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT YEAR(enrolment_date) AS year, COUNT(id) AS inscriptions FROM uni.students GROUP BY year ORDER BY year;
```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT COUNT(id), office_address FROM uni.teachers GROUP BY office_address ORDER BY office_address;
```

3. Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT AVG(vote), exam_id FROM uni.exam_student GROUP BY exam_id;
```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT COUNT(id), department_id  FROM uni.degrees GROUP BY department_id;
```
