## для старта работы с MySQL c mac
```cmd
mysql -u root -p
```

## просмотр баз данных
```cmd
SHOW DATABASES;
```

## использование db
```cmd
USE название_базы_данных;
```

## просмотр таблиц в db
```cmd
SHOW TABLES;
```

## просмотр структуры таблицы
```cmd
DESCRIBE teacher;
SHOW COLUMNS FROM lesson;
```

## получение всех данных из таблицы
```cmd
SELECT * FROM teacher;
```

## получение всех id из таблицы (зависимо от данных таблицы)
```cmd
SELECT id FROM teacher;
```

## получение всех surname из таблицы (зависимо от данных таблицы)
```cmd
SELECT surname FROM teacher;
```

## получение всех данных у которых значение схож с query
```cmd
SELECT * FROM teacher WHERE surname = "Quasar";
```

## получение всех данных с лимитом
```cmd
SELECT * FROM teacher WHERE surname = "Quasar" limit 10;
```

## сортировка по заданному полю
```cmd
SELECT * FROM teacher ORDER BY surname;
SELECT * FROM teacher ORDER BY id;
```

## сортировка по заданному полю в обратном порядке
```cmd
SELECT * FROM teacher ORDER BY id DESC;
```

## добавление нового поля к таблице
```cmd
ALTER TABLE teacher ADD age INT;
```

## изменение значение поля у колонки таблицы (здесь по id)
```cmd
UPDATE teacher SET age = 20 WHERE id = 1;
```

## изменение всех значений у таблицы
```cmd
UPDATE teacher SET age = 20;
```

## поиск данных у которых значение заканчивается на ar
```cmd
SELECT * FROM teacher WHERE surname LIKE "%ar";
```

## поиск данных у которых значение начинается c Q
```cmd
SELECT * FROM teacher WHERE surname LIKE "Q%";
```

## получение данных с условием (AND, OR)
```cmd
SELECT * FROM teacher WHERE id > 3 AND age > 30;
SELECT * FROM teacher WHERE id > 3 AND age < 40;
SELECT * FROM teacher WHERE id > 5 OR age < 25;
```

## получение данных с отрицательным условием
```cmd
SELECT * FROM teacher WHERE NOT id = 2;
```

## получение данных у которых поле age равен 35 либо 40
```cmd
SELECT * FROM teacher WHERE age BETWEEN 35 AND 40;
```

## удаление данных по id
```cmd
DELETE FROM teacher WHERE id = 7;
```

## добавление нескольких данных в таблицу
```cmd
INSERT INTO lesson (name, teacher_id) 
VALUES ("Математика", 1), 
("Информатика", 1), 
("Русский", 2), 
("Физика", 3);
```

## Связывает таблицы teacher и lesson по ID.
```cmd
SELECT teacher.surname, lesson.name 
FROM teacher 
INNER JOIN lesson 
ON teacher.id = lesson.teacher_id;
```