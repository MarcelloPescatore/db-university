# 1
# SELECT * FROM `students` WHERE year(`date_of_birth`) = 1990;

# 2
# SELECT * FROM `courses` WHERE `cfu` > 10

# 3
# SELECT * FROM `students` WHERE `date_of_birth` < '1994-12-05'

# 4
# SELECT * FROM `courses` WHERE `period` = 'I semestre' AND `year` = 1

# 5
# SELECT * FROM `exams` WHERE `date` = '2020-06-20'  AND `hour` > '14:00:00'

# 6
# SELECT * FROM `degrees` WHERE `level` = 'magistrale'

# 7
# SELECT COUNT(DISTINCT `id`) AS number_of_departments FROM `departments`

# 8
# SELECT COUNT(*) AS teachers_without_phone FROM `teachers` WHERE `phone` IS NULL 

# 9
# INSERT INTO `students` (degree_id, name, surname, date_of_birth, fiscal_code, enrolment_date, registration_number, email)
# VALUES (12, 'Marcello', 'Pescatore', '1999-09-16', 'HAKJOH189U309', '2024-04-12', '1976', 'example@mail.com')
# SELECT * FROM `students` WHERE `name` = 'Marcello'

# 10
# SELECT * FROM `teachers` WHERE `name` = 'Pietro' AND `surname` = 'Rizzo'
# UPDATE `teachers` SET `office_number` = 126 WHERE `id` = 58 AND `name` = 'Pietro' AND `surname` = 'Rizzo'

# 11
# DELETE FROM `students` WHERE `id` = 5002
# SELECT * FROM `students` WHERE `name` = 'Marcello'
