CREATE TABLE books(  
    id int NOT NULL PRIMARY KEY AUTO_INCREMENT COMMENT 'Primary Key',
    title VARCHAR(255)
) COMMENT 'Table storing information about books in the service';

CREATE TABLE authors(  
    id int NOT NULL PRIMARY KEY AUTO_INCREMENT COMMENT 'Primary Key',
    name VARCHAR(255),
    middlename VARCHAR(255),
    lastname VARCHAR(255)
) COMMENT 'Table storing information about authors in the service';

CREATE TABLE authors_books(  
    id_authors int NOT NULL,
    id_books int NOT NULL,
    PRIMARY KEY (id_authors, id_books),
    Foreign Key (id_authors) REFERENCES authors (id),
    Foreign Key (id_books) REFERENCES books (id) 
) COMMENT '';

INSERT authors (name, middlename, lastname)
VALUES 
('Сергей', 'Александрович', 'Петров'),
('Иван', 'Сергеевич', 'Алексеев'),
('Александр', 'Александрович', 'Сидоров'),
('Ян', 'Иванович', 'Жуков')

INSERT books (title)
VALUES 
("Зависимые"),
("Одинокий путь"),
("Красная зона"),
("Твои несбыточные мечты"),
("Река скорби"),
("Неизвестный номер")