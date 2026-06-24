# SQL-6
SELECT
    class,
    COUNT(*) AS oquvchilar_soni,
    AVG(grade) AS ortacha_baho
FROM students
GROUP BY class;

SELECT
    class,
    AVG(grade) AS ortacha_baho
FROM students
GROUP BY class
HAVING AVG(grade) > 80;

SELECT
    class,
    age,
    COUNT(*) AS oquvchilar_soni,
    AVG(grade) AS ortacha_baho
FROM students
GROUP BY class, age
ORDER BY class, age;

SELECT
    class,
    COUNT(*) AS uquvchilar_soni,
    STRING_AGG(name, ', ' ORDER BY name) AS uquvchilar_ruyxati
FROM students
GROUP BY class;

SELECT
    class,
    COUNT(*) AS uquvchilar_soni,
    AVG(grade) AS urtacha_baho
FROM students
WHERE grade >= 50  -- 1. Oldin past baholarni o'chirib tashlaymiz
GROUP BY class     -- 2. Keyin sinflarga ajratamiz
HAVING COUNT(*) > 5; -- 3. Oxirida faqat o'quvchisi 5 tadan ko'p sinflarni qoldiramiz

-- BU SO'ROV XATOLIK BERADI!
SELECT class, name, AVG(grade)
FROM students
GROUP BY class;
