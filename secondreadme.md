# QUERY GROUP BY:

- 1. Contare quanti iscritti ci sono stati ogni anno

### Query da eseguire:

    SELECT COUNT('numero iscritti'),YEAR(`enrolment_date`) AS 'Anno di immatricolazione'
    FROM `students`
    GROUP BY YEAR(`enrolment_date`);

- 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

### Query da eseguire:

    -

- 3. Calcolare la media dei voti di ogni appello d'esame

### Query da eseguire:

    -

- 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

### Query da eseguire:

    -

# QUERY JOIN:

- 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

### Query da eseguire:

    -

- 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
     Neuroscienze

### Query da eseguire:

    -

- 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

### Query da eseguire:

    -

- 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
     sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
     nome

### Query da eseguire:

    -

- 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

### Query da eseguire:

    -

- 6. Selezionare tutti i docenti che insegnano nel Dipartimento di
     Matematica (54)

### Query da eseguire:

    -

- 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
     per ogni esame, stampando anche il voto massimo. Successivamente,
     filtrare i tentativi con voto minimo 18.

### Query da eseguire:

    -
