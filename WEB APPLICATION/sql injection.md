## sql basic
- it has a database , like we usually have servers where data is stored.
1. Get all users : 
- select * from users; 
- * means all, users is a column after the whole thing
2. from a specific user
- select * from users where username = 'alice';
### how login works
- enter your credentials, then build sql query, then send a request to the database, then match found or not found.
- SELECT * FROM users WHERE username = 'alice' AND password = 'pass1234';
- AND is a true condition, if botht the statements are true then the result will be true. 
- for hacker : - SELECT * FROM users WHERE username = 'alice'-- AND password = 'anything';
- -- is to make the later part a comment
- - SELECT * FROM users WHERE username = 'alice' or 1=1 --;
- or condition is that if one is true and another one is false, it results into true.
## SQL Injection
- when you can manipulate the SQL queries that the web application sends to its database.
- The consequences can be severe: unauthorised access to sensitive data, bypassed authentication, modified or deleted records, and in some cases, full control of the database server itself.
