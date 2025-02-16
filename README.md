# Mastering-SQL-Functions
A project showcasing various SQL functions with examples and queries.

This project involves modifying the Persons table by adding a DOB column and creating a user-defined function to calculate age. It also includes SQL queries to fetch age using the function, analyze country names by finding their length, extracting the first three characters, and converting them to uppercase and lowercase in the Country table.

1. Add a new column called DOB in Persons table with data type as Date.
    alter table persons add column DOB date;
2. Insert records to the newly created column

   UPDATE Persons SET DOB = '1990-05-15' WHERE Id = 1;
    UPDATE Persons SET DOB = '1985-10-20' WHERE Id = 2;
    UPDATE Persons SET DOB = '1992-08-25' WHERE Id = 3;
    UPDATE Persons SET DOB = '1988-03-10' WHERE Id = 4;
    UPDATE Persons SET DOB = '1995-12-05' WHERE Id = 5;
    UPDATE Persons SET DOB = '1993-07-18' WHERE Id = 6;
    UPDATE Persons SET DOB = '1987-04-22' WHERE Id = 7;
    UPDATE Persons SET DOB = '1998-09-30' WHERE Id = 8;
    UPDATE Persons SET DOB = '1991-06-11' WHERE Id = 9;
    UPDATE Persons SET DOB = '1984-02-14' WHERE Id = 10;
    UPDATE Persons SET DOB = '1996-11-29' WHERE Id = 11;
    UPDATE Persons SET DOB = '1989-01-17' WHERE Id = 12;
    UPDATE Persons SET DOB = '1997-05-23' WHERE Id = 13;
    UPDATE Persons SET DOB = '1986-08-07' WHERE Id = 14;
    UPDATE Persons SET DOB = '1994-03-19' WHERE Id = 15;
    UPDATE Persons SET DOB = '1990-12-25' WHERE Id = 16;
    UPDATE Persons SET DOB = '1983-10-03' WHERE Id = 17;
    UPDATE Persons SET DOB = '1999-07-12' WHERE Id = 18;
    UPDATE Persons SET DOB = '2000-04-09' WHERE Id = 19;
    UPDATE Persons SET DOB = '1981-06-15' WHERE Id = 20;
    UPDATE Persons SET DOB = '1992-09-27' WHERE Id = 21;
    UPDATE Persons SET DOB = '1980-11-05' WHERE Id = 22;
   3. Write a user-defined function to calculate age using DOB.
    delimiter ##

    create function calage(DOB date)
    returns int
    deterministic
 
    BEGIN
	    return TIMESTAMPDIFF(year,DOB,curdate());
    END ##
    DELIMITER ;
   4. Write a select query to fetch the Age of all persons using the function that has been created.
      
        select concat(fname,' ',Lname) as Name , DOB, calage(DOB) as Age from Persons;
      
   5. Find the length of each country name in the Country table.
   
         select country_name, length(country_name)  from country;

   6. Extract the first three characters of each country's name in the Country table.

        select country_name,substr(country_name,1,3)  from country;

   7. Convert all country names to uppercase and lowercase in the Country table.

        select country_name, upper(country_name),lower(country_name) from country;

   
