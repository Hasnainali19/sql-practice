🎵 SQL Practice – WSDA_Music Dataset
📌 Overview

This project contains SQL queries executed on the WSDA_Music dataset using SQLite.
It demonstrates basic SQL operations including filtering, sorting, and conditional logic.

✅ Tools & Setup

Database: WSDA_Music

Software: SQLite Browser

Language: SQL

🔑 Concepts Practiced

SELECT – Retrieving fields

FROM – Specifying tables

WHERE – Filtering rows

ORDER BY – Sorting results

LIMIT - For Limited data

LIKE – Pattern matching

BETWEEN ... AND – Range filtering

IN – Checking multiple values

CASE – Conditional output

🛠 Example Queries
/*
Name : Hasnainali Saiyed
Date : 21-08-2025
Description : Query to display all customers First,Last Names and Email Address
*/

SELECT
	FirstName AS "Customer FirstName",
	LastName AS "Customer LastName",
	Email AS EMAIL
FROM
	Customer


/*
Name : Hasnainali Saiyed
Date : 21-08-2025
Description : How many of the customers purchased two songs at $0.99 each ?
*/


SELECT
	InvoiceDate,
	BillingAddress,
	BillingCity,
	total
FROM 
	Invoice
WHERE
	total = 1.98
ORDER BY
	InvoiceDate


-- WSDA Music Sales Goals:
-- 	They want as many as customers aspossible to spend between $7:00 and %15:00
-- Sales Category 
-- Baseline Purchase - Between $0.99 AND $1.99
-- Low Purchase - Between $2.00 and $6.99
-- Target Purchase $7.00 AND $15.00

SELECT
	InvoiceDate,
	BillingCity,
	BillingAddress,
	total,
	CASE
	WHEN total < 0.99 THEN "Baseline Purchase"
	WHEN total BETWEEN 2.00 AND 6.99 THEN "Lower Purchase"
	WHEN total BETWEEN 7.00 AND 15.00 THEN "Target Purchase"
	ELSE "Top Performance"
	END AS "Purchase type"
FROM 
	Invoice
WHERE
	"Purchase type" = "Top Performance"
ORDER BY
	BillingCity



/*
Name : Hasnainali Saiyed
Date : 21-08-2025
Description : Get all the billing cities that are grater than 1.98 from anyother cities that starts with P or starts with D?

PEMDAS : Parenthesis , Exponent , Mulitplication , Divison , Addition , Subtraction 
BEMDAS : Brackets , Exponent , Mulitplication , Divison , Addition , Subtraction 
*/

SELECT
	InvoiceDate,
	BillingAddress,
	BillingCity,
	total
FROM 
	Invoice
WHERE
	total > 1.98 AND (BillingCity LIKE 'P%' OR BillingCity LIKE 'D%')
ORDER BY
	InvoiceDate

 <0img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/602274be-2c2e-4705-a11d-ca796f48db38" />

 <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a24d8c9f-c4fa-43b5-9b19-541eafe132d7" />

 <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5f2ca2a4-aeef-42ab-b69b-e582700d71ce" />


![Uploading image.png…]()

