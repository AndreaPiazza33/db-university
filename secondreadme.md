# QUERY GROUP BY:

- 1. Contare quanti iscritti ci sono stati ogni anno

### Query da eseguire:

    SELECT COUNT('numero iscritti'),YEAR(`enrolment_date`) AS 'Anno di immatricolazione'
    FROM `students`
    GROUP BY YEAR(`enrolment_date`);

- 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

### Query da eseguire:

    SELECT COUNT(id), `office_address`
    FROM `teachers`
    GROUP BY `office_address`;

- 3. Calcolare la media dei voti di ogni appello d'esame

### Query da eseguire:

    SELECT AVG(`vote`) AS 'media voto', `exam_id` AS 'appello esame'
    FROM `exam_student`
    GROUP BY `exam_id`;

- 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

### Query da eseguire:

    SELECT COUNT('numero corsi di laurea'), `department_id` AS 'dipartimento'
    FROM `degrees`
    GROUP BY `department_id`;

# QUERY JOIN:

- 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

### Query da eseguire:

    SELECT *
    FROM `students`
    INNER JOIN `degrees`
    ON degrees.id = students.degree_id
    WHERE degrees.name = 'Corso di Laurea in Economia';

- 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
     Neuroscienze

### Query da eseguire:

    SELECT *
    FROM `degrees`
    INNER JOIN `departments`
    ON degrees.department_id = departments.id
    WHERE degrees.level = 'Magistrale'
    AND departments.name = 'Dipartimento di Neuroscienze';

- 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

### Query da eseguire:

    SELECT `courses`.*
    FROM `courses`
    JOIN `course_teacher`
    ON `courses`.`id` = `course_teacher`.`course_id`
    JOIN `teachers`
    ON `course_teacher`.`teacher_id` = `teachers`.`id`
    WHERE `teachers`.`id` = 44;

- 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
     sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
     nome

### Query da eseguire:

    SELECT `students`.`surname`,`students`.`registration_number`,`degrees`.`name`,`departments`.`name`
    FROM `students`
    JOIN `degrees`
    ON `students`.`degree_id`= `degrees`.`id`
    JOIN `departments`
    ON `degrees`.`department_id` = `departments`.`id`
    ORDER BY `students`.`surname`, `students`.`name`;

- 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

### Query da eseguire:

    SELECT `degrees`.`name`,`courses`.`name`,`courses`.`period`,`courses`.`year`,`courses`.`cfu`,`teachers`.`name`,`teachers`.`surname`
    FROM `degrees`
    JOIN `courses`
    ON `degrees`.`id` =`courses`.`degree_id`
    JOIN `course_teacher`
    ON `courses`.`id` = `course_teacher`.`course_id`
    JOIN `teachers`
    ON `course_teacher`.`teacher_id` =`teachers`.`id`;

- 6. Selezionare tutti i docenti che insegnano nel Dipartimento di
     Matematica (54)

### Query da eseguire:

    SELECT DISTINCT `teachers`.`name`,`teachers`.`surname`,`teachers`.`phone`,`teachers`.`email`,`teachers`.`office_address`,`teachers`.`office_number`
    FROM `teachers`
    JOIN `course_teacher`
    ON `teachers`.`id` =`course_teacher`.`teacher_id`
    JOIN `courses`
    ON `course_teacher`.`course_id` = `courses`.`id`
    JOIN `degrees`
    ON `courses`.`degree_id` = `degrees`.`id`
    JOIN `departments`
    ON `degrees`.`department_id` = `departments`.`id`
    WHERE `departments`.`name` = "Dipartimento di Matematica";

- 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
     per ogni esame, stampando anche il voto massimo. Successivamente,
     filtrare i tentativi con voto minimo 18.

### Query da eseguire:

    -
