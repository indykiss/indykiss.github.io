---
layout: post
title:      "SQL Refresh"
date:       2019-11-11 19:13:08 +0000
permalink:  sql_refresh
---



Let's check out data management techniques with SQL. <br>


We can begin by making a database with "CREATE DATABASE name_db" and delete a database with "DROP DATABASE name_db." Or make a table with "CREATE TABEL name_table(column_name1, column_name2, etc)." Delete a table with "DROP TABLE table_name." <br>

What can we do with SQL? <br>

- Please note that the asterik sometimes disappears with the Learn blog system (not sure why; submitting a bug and will try to add in a fix!). The Select then (insert things suddenly italicized for no reason) means that there should be Select then an asterik. <br>

<br>
####  Selecting Data 

Let's take a simple table and create queries to get the data we need. 
<br>

**Pets table:<br>
**

|ID    | Name   |  Species   |  Age|
| -------- | -------- | -------- |
|1    |  Bloop  |    Dog         |    5|
|2    |  Kit         |   Cat          |     2|
|3    |  Chili       |  Fish       |       0.5|
|4   |   Andy     |  Lemur  |       10|
|5  |    Indy       |  Dog     |        1|
|6 |     Meep    |  Dog    |          5|

Well, we can select values based on whatever parameters we want:

SELECT * FROM Pets;<br>
// All the records from pets<br>
<br>
SELECT ID, Species FROM Pets; <br>
// Pull out the ID and species from Pets<br>
<br>
SELECT DISTINCT Species FROM Pets;<br>
// Select only the unique values from the species column<br>
<br>
SELECT *  FROM Pets WHERE Species = "Dog"; <br>
// Finds all our puppies <br>
<br>
SELECT * FROM Pets WHERE NOT Species  = "Dog"; <br>
// Finds everything except our puppies <br>
<br> 
SELECT * FROM Pets WHERE Species = "Dog" AND ID > 3; <br>
// Finds all the puppies and all the puppies who have an ID > 3 <br>
// Instead of AND, we can do OR <br>
<br>
SELECT * FROM Pets ORDER BY Name, Species;<br>
// Let's make this table in alphabetical order by name, then by species<br>
<br>
SELECT * FROM Pets ORDER BY Name DESC;<br>
// Reverse alphabetical order<br>
<br>
<br>
####  Adding data

Let's take the same table and practice manupulating records in the table. We can add, track down bad data, update that bad data, or delete data. 


**Pets table:<br>**

|ID    | Name   |  Species   |  Age|
| -------- | -------- | -------- |
|1    |  Bloop    |     Dog      |    5|
|2    |  Kit          |   Cat          |     2|
|3    |  Chili       |  Fish         |       0.5|
|4    |  Andy     |  Lemur     |       10|
|5    |  Indy       |  Dog         |        1|
|6    |  Meep    |  Dog        |      5|



INSERT INTO Pets (Name, Species, Age) VALUES (Fluffy, Dog, 6);<br>
// Add a new dog into the table<br>
<br>
SELECT * FROM Pets WHERE Species IS NULL;<br>
// Let's find where the species was left blank... or if want not blank- "IS NOT NULL"<br>
<br>
UPDATE Pets SET Species = "Doggo" WHERE Species = "Dog";
// Update things! Instead of Dog, we want to call the species Doggo<br>
<br>
UPDATE Pets SET Species = "Doggo", Age = "∞" WHERE ID = 5; <br>
// Update multiple things at once! <br>
<br>
DELETE FROM Pets WHERE Age = "∞"; <br>
// Delete the dog that never dies <br>
<br>
TRUNCATE TABLE Pets; <br>
// Clear the data in the table. <br>
<br>
ALTER TABLE Pets ADD Color STRING; <br>
// Add a new column, Color with string data type. <br>
 <br>
ALTER TABLE Pets DROP COLUMN Color; <br>
// Drop that new column Color. <br>

<br>
####  Finding all that match  


Let's take the same table, minus the above alterations, and practice filtering by specific parameters. 

**Pets table:<br>**

|ID    | Name   |  Species   |  Age|
| -------- | -------- | -------- |
|1    |  Bloop    |     Dog      |    5|
|2    |  Kit          |   Cat          |     2|
|3    |  Chili       |  Fish         |       0.5|
|4    |  Andy     |  Lemur     |       10|
|5    |  Indy       |  Dog         |        1|
|6    |  Meep    |  Dog        |      5|


SELECT MIN(Age) FROM Pets; 
<br>
// Let's find the youngest pet. Oldest pet would be MAX(age). Average is AVG(Age). Sum is SUM(Age). <br>
<br>
SELECT COUNT( * ) FROM Pets WHERE Age = 5 ;<br>
// Count how many dogs are 5. <br>
<br>
SELECT * FROM Pets WHERE Name LIKE 'b%'; <br>
// Find the pets with names that start with 'b' OR looking for ends with: '%b' OR contains 'b' would be '%b%' OR starts with 'a' and ends with 'b' 'a%b'<br>
<br>
SELECT * FROM Pets WHERE Name NOT LIKE ' b% '; <br>
// Find the pets' names that don't start with the letter 'b' OR first letter is not a certain letters, LIKE '[^acf]%'<br>
<br>
SELECT * FROM Pets WHERE Name LIKE '_a%' ; <br>
//  Find the pets' where the second letter in the name is 'n' <br>
<br>
SELECT * FROM Pets WHERE Name LIKE '[aeiou]%'; <br>
// Find all the pets whose names start with a vowel OR I want a-m, we can do '[a-m]%' <br>
<br>
SELECT * FROM Pets WHERE Age IN ("2", "5"); <br>
// Select the pets that are 2 or 5. <br>
<br>
SELECT * FROM Pets WHERE Age NOT IN ("2", "5"); <br>
// Select the pets that are aged anything except 2 or 5.<br>
<br>
SELECT * FROM Pets WHERE Age BETWEEN 2 AND 10; <br>
// Select the pets that are aged between 2 and 10.<br>
 <br>
SELECT Name, Species AS Spc, Age FROM Pets; <br>
// Make an alias of the column Species to Spc <br>
<br>
SELECT COUNT(ID) FROM Pets GROUP BY Species; <br>
// Let's count all the animals, grouped by species. <br>

<br>
#### Join tables, AKA Combining tables

Now we'll go over how to join tables together to become one table. This is really a staple of breaking down data silos to integrate across boundaries and make data analysis easier. 


**Pets table:<br>**

|ID    | Name   |  Species   |  Age|
| -------- | -------- | -------- |
|1    |  Bloop    |     Dog      |    5|
|2    |  Kit          |   Cat          |     2|
|3    |  Chili       |  Fish         |       0.5|
|4    |  Andy     |  Lemur     |       10|
|5    |  Indy       |  Dog         |        1|
|6    |  Meep    |  Dog        |      5|


**Wild_animal_friends table:<br>**

|ID    | Name   |  Species   |  Age| PetFriendID|
| -------- | -------- | -------- | -------- |
|1    |  Alpha    |     Wolf      |    6| 6|
|2    |  Tiny          |   Elephant          |     1| 5|
|3    |  Simba       |  Lion         |       0.5| 4|
|4    |  Cheez-It     |  Cheetah     |       5| 3|
|5    |  Beta       |  Wolf         |        1| 2|
|6    |  Mufasa    |  Lion        |      2| 1|


SELECT * FROM Pets LEFT JOIN Wild animal friends ON Pets.ID = Wild_animal_friends.PetFriendID; <br>
// Lets us join the pets and wild animals table based on the relationship of Pet Friend ID and Pet's ID. <br>
<br>
SELECT * FROM Pets INNER JOIN Wild_animal_friends ON Pets.ID = Wild_animal_friends.PetFriendID <br>
// Let's see all the records where there is a match in *both* tables. <br>

<br>

<br>Thanks for reading! That's it for now. I'll dive deeper into SQL joins next week.<br>
Indy<br>

