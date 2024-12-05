-- Contare quanti iscritti ci sono stati ogni anno
/* SELECT YEAR(`enrolment_date`), COUNT(*) AS numero_iscritti
FROM `students`
GROUP BY YEAR(`enrolment_date`) */

-- Contare gli insegnanti che hanno l'ufficio nello stesso edificio
/* SELECT `office_address`, COUNT(*) AS numero_insegnanti
FROM `teachers`
GROUP BY `office_address` */

-- Calcolare la media dei voti di ogni appello d'esame
/* SELECT `exams`.`course_id`, AVG(`exam_student`.`vote`) AS media_voti
FROM `exams`
JOIN `exam_student` ON `exams`.`id` = `exam_student`.`exam_id`
GROUP BY `exams`.`course_id` */

-- Contare quanti corsi di laurea ci sono per ogni dipartimento
/* SELECT `degrees`.`department_id`, COUNT(*) AS numero_corsi
FROM `degrees`
GROUP BY `department_id` */

-- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
/* SELECT `students`.`id`, 
`students`.`name`, 
`students`.`surname`, 
`students`.`enrolment_date`, 
`degrees`.`name`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name`= 'Corso di Laurea in Economia' */

-- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
/* SELECT `degrees`.`name`,
`degrees`.`id`,
`departments`.`name` AS department_name
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `degrees`.`level` = 'magistrale' AND `departments`.`name` = 'Dipartimento di Neuroscienze' */

-- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
/* SELECT `courses`.`id` AS id_corso,
`courses`.`name`,
`teachers`.`name`,
`teachers`.`surname`
FROM `courses`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`
WHERE `teachers`.`id` = 44 */

-- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nomE
/* SELECT `students`.`id`,
`students`.`name`,
`students`.`surname`,
`degrees`.`name` AS corso_di_laurea,
`departments`.`name` AS Dipartimento
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname`, `students`.`name` */

-- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
/* SELECT `degrees`.`name` AS corso_di_laurea,
`courses`.`name` AS corso,
`teachers`.`name` AS nome_del_professore,
`teachers`.`surname` AS cognome_del_professore
FROM `degrees`
JOIN `courses` ON `courses`.`degree_id` = `degrees`.`id`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`;*/

-- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
/* SELECT DISTINCT `teachers`.`id`,
`teachers`.`name`,
`teachers`.`surname`,
`departments`.`name`
FROM `teachers`
JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id`
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica' */