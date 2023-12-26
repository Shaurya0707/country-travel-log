This is full-stack web development project ceated using HTML, CSS, JavaScript, Node.js, Express.js, EJS and relational database postgreSQL. It is a family travel tracker which consists a world map, different family members can be added in it, and each member can assign different colours for them and can add countries they have visited on the world map.

In order to use this project on your pc, follow these steps:-
1) Import the required node modules.

2) Download postgreSQL and pgAdmin, and create your own password while installation.

3) After downloading postgreSQL, create a database named world or any other name you like.

4) Create two tables in it named visited_countries, users.

5) Create a table name countries and import the country data from the countries sheet given by me in this repository.

6) Use the below given sql codes to create table's schema's and add data in it :- 

CREATE TABLE users(
id SERIAL PRIMARY KEY,
name VARCHAR(15) UNIQUE NOT NULL,
color VARCHAR(15)
);

CREATE TABLE visited_countries(
id SERIAL PRIMARY KEY,
country_code CHAR(2) NOT NULL,
user_id INTEGER REFERENCES users(id)
);

INSERT INTO users (name, color)
VALUES ('Shaurya', 'teal'), ('Member', 'powderblue');

INSERT INTO visited_countries (country_code, user_id)
VALUES ('IN', 1), ('IN', 2);

SELECT *
FROM visited_countries
JOIN users
ON users.id = user_id; 