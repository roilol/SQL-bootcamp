# SQL-bootcamp
PostgreSQL Note


Databases: systems that allow users to store and organize data - useful when dealing with large amounts of data
    -pros: Data integrity (anyone can't access and change the data)
           Massive amounts of data
           Quickly combine different datasets
           Automate steps for re-use
           Can support data for websites and applications
           
SQL Statement Fundamentals

1. SELECT * or column1, column2 ... FROM table_name;
          
          i.e. SELECT first_name, last_name, email address FROM customer;

2. SELECT DISTINCT = returns only distinct(different) values without duplicates.
      
      i.e. SELECT DISTINCT rating FROM film;
      
3. SELECT WHERE = shows values satisfying certain conditions
      
      i.e. SELECT column1, colum2
           FROM table_name
           WHERE conditions; (=, >, <, >=, <=, "<> or !="=not equal)
           
4. COUNT = retruns the numbers of input rows that match a specific condition of a query.
  
  i.e SELECT COUNT (*) or (column) FROM table_name;
      
      SELECT COUNT (customer_id) FROM customer; = count the number of rows in the customer_id column from customer table.
     
      SELECT COUNT (DISTINCT (customer_id)) FROM customer; = count the distinct number of rows in the custtomer_id column from customer table

5. LIMIT = allows you to limit the number of rows you get back after a query
           useful when watning to get all coumns but not all rows
           goes at the end of a query
          
          i.e SELECT * FROM customer LIMIT 25;
          
6. ORDER BY = allows you to sort the rowsz returned from the SELECT statement in ascending or descending order based on criteria specified.

      i.e  SELECT first_name, last_name
           FROM customer
           ORDER BY first_name ASC;
    
           SELECT first_name 
           From customer 
           ORDER BY last_name DESC  
           LIMIT 10; ---------- only postgreSQL allows you not to put last_name into the SELECT statement.
           
           Q1. Get the customer ID number for the top 10 highest payment amounts
           >SELECT customer_id, amount FROM payment ORDER BY amount DESC LIMIT 5;
           
           Q2. Get the titles of the movies with film ids 1-5
           >SELECT title, film_id FROM film ORDER BY film_id ASC LIMIT 5;
         
           
7. WHERE BETWEEN = to match a value against a range of values
    
     i.e SELECT amount, paymnet_date FROM paymet WHERE payment_date BETWEEN '2007-02-07' ANd '2007-02-15';
     
     
8. IN = You use the IN operator with the WHERE clause to check if a value matches any value in a list of values.
        Returns true if the value matches any value in the list. The list of vlaues is not limited to a list of numbers or string
        but also a result set of a SELECT statement as shown in the follwing query
        > value IN (SELECT value FROM table_name)
        
        i.e SELECT customer_id, rental_id, retrun date FROM rental WHERE customer_id IN (1,2) ORDER BY return_date DESC;
           = SELECT customer_id, rental_id, retrun date FROM rental WHERE customer_id = 1 OR customer_id = 2 ORDER BY return_date DESC;
           
           
 9. LIKE = the manager asks you find a customer that he doesn't remember the name exactly. He just rememers that customer's first name begins 
           with something like Jen.
           
           Use wildcard character such as "_" ,"%".
           
           i.e SELECT first_name, last_name FROM customer WHERE first_name LIKE 'Jen%'

           Variation >> LIKE '%y'; >> names ended by ' y ' 
               
                        LIKE '%er%' >> names containing 'er' somewhere in their names
                        
                        ILIKE: for matching values without case sensitivity
                        ILIKE 'BAR%'; = 'BaR%'; ='bAR%' etc
                        
     General Challenge 1
     
     Q.1 How many paymenet trasactions were greater than $5.00?
     
     A.1 >SELECT COUNT (amouunt) FROM payment WHERE amount >5;
     
     
     Q2 How many actors have a first name that starts with letter P?
     
     A2 > SELECT COUNT (*) FROM actor WHERE first_name LIKE 'P%';
     
     Q3 How many unique districts are our customers from?
     
     A3 SELECT COUNT (DISTINCT (district)) FROM address;
     
     Q4 Retrieve the list of names for those distinct districts from the previous question.
     
     A4 SELECT DISTINCT (distirct) FROM address;
     
     Q5 How many films have a rating of R and a replacement cost between $5 and $15?
     
     A5 SELECT COUNT (*) FROM film WHERE rating = 'R' AND replacement_cost BETWEEN 5 and 15;
     
     Q6 How many films have the word Truman somewhere in the title?
     
     A6 SELECT COUNT (*) FROM film WHERE title LIKE '%Truman%'
