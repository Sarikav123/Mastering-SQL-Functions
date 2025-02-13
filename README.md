# Mastering-SQL-Functions
A project showcasing various SQL functions with examples and queries.

This project involves modifying the Persons table by adding a DOB column and creating a user-defined function to calculate age. It also includes SQL queries to fetch age using the function, analyze country names by finding their length, extracting the first three characters, and converting them to uppercase and lowercase in the Country table.

1. Add a new column called DOB in Persons table with data type as Date.
    alter table persons add column DOB date;
2. Write a user-defined function to calculate age using DOB.
