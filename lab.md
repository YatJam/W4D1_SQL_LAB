# SQL Lab

The Springfield Cinema is having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.
SELECT movies.title FROM movies

Iron Man
The Incredible Hulk
Iron Man 2
Thor
Captain America: The First Avenger
Avengers Assemble
Iron Man 3
Thor: The Dark World
Batman Begins
Captain America: The Winter Soldier
Guardians of the Galaxy
Avengers: Age of Ultron
Ant-Man
Captain America: Civil War
Doctor Strange
Guardians of the Galaxy 2
Spider-Man: Homecoming
Thor: Ragnarok
Black Panther

2.  Return ONLY the name column from the 'people' table
SELECT people.name FROM people

Homer Simpson
Marge Simpson
Lisa Simpson
Maggie Simpson
Patty Bouvier
Selma Bouvier
Kent Brockman
Ned Flanders
Barney Gumble
Itchy
Eric Cartman
Scratchy
Crusty the Clown
Montgomery Burns
Mayor Joe Quimby
Groundskeeper Willie

3.  Oops! Someone spelled Krusty The Clown's name wrong! Change it to reflect the proper spelling (Crusty should be Krusty).
UPDATE people
SET name='Krusty the Clown'
WHERE id = 13;

UPDATE 1

4.  Return ONLY Homer Simpson's name from the 'people' table.
SELECT people.name FROM people WHERE id = 1

Homer Simpson

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.
DELETE FROM movies
WHERE id = 9

DELETE 1

6.  We forgot one of the main characters! Add Bart Simpson to the 'people' table
INSERT INTO people( name)
VALUES ('Bart Simpson');

INSERT 0 1

7.  Eric Cartman has decided to hijack our movie evening, Remove him from the table of people.
DELETE FROM people
WHERE id = 11

DELETE 1

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.
INSERT INTO movies (title, year, show_time)
VALUES ('Avengers: Infinity War', '2018', '00:00');

INSERT 0 1

9.  The cinema would like to make the Iron Man movies a triple billing. Find out the show time of "Iron Man 2" and set the show time of "Iron Man 3" to start two hours later.
SELECT movies.show_time FROM movies WHERE id = 3;
18:45
UPDATE movies
SET show_time='20:45'
WHERE id = 7;
UPDATE 1

## Extension

1.  Research how to delete multiple entries from your table in a single command.
DELETE FROM people
WHERE id IN (4, 6, 9)

DELETE 3
