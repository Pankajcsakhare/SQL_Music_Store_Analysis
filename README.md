# SQL Music Store Analysis
SQL project to analyze online music store data

Database and Tools
Postgre SQL
PgAdmin4

# Schema- Music Store Database
 ![Image Alt](https://github.com/Pankajcsakhare/SQL_Music_Store_Analysis/blob/4e33a9082cbdd6116d5b698c1e1283e1ce9291de/MusicDatabaseSchema.png)

Question Set 1 
Q1: Who is the senior most employee based on job title?
SELECT title, last_name, first_name 
FROM employee
ORDER BY levels DESC
LIMIT 1

Q2: Which countries have the most Invoices?
SELECT COUNT(*) AS c, billing_country 
FROM invoice
GROUP BY billing_country
ORDER BY c DESC

Q3: What are top 3 values of total invoice?
SELECT total 
FROM invoice
ORDER BY total DESC

Q4: Which city has the best customers? We would like to throw a promotional Music Festival in the city we made the most money. 
Write a query that returns one city that has the highest sum of invoice totals. 
Return both the city name & sum of all invoice totals
SELECT billing_city,SUM(total) AS InvoiceTotal
FROM invoice
GROUP BY billing_city
ORDER BY InvoiceTotal DESC
LIMIT 1;
