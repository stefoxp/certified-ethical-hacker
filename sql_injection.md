# SQL Injection

## SQL Injection concepts

... is a basic attack used to gain unauthorized access to a db or retrieve information from a db

It is a flaw in web application and not a db or web server issue

It is a major issue for all db-driven websites

... can be used to implement the following attacks:

- **Authentication bypass**: an attacker logs onto an application without providing a valid username
- **Authorization bypass**: an attacker alters authorization information stored in the db
- **Information disclosure**: an attacker obtains sensitive information
- **Compromised data integrity**: an attacker defaces a web page, insert malicious content, or alters the contents
- **Compromised availibility of data**: an attacker deletes the db information, delete logs, or audit information
- **Remote code execution**: an attacker compromises the host OS

All relational db are susceptible to ...

... target websites and web apps that do not follow secure coding practices

### Examples of SQL injection

- on login form
- on search field
- on forgot password form

## Types of SQL injection

![Types of SQL injection](img/sql_injection_types.png)

### In-band

An attacker uses the same communication channel to perform the attack and retrive the results.

#### Error-based

Intentionally inserts bad inputs into an application, causing it to return db errors.

#### system stored procedure

Exploits db stored procedures.

If the web application does not sanitize the user inputs to dynamically construct SQL statements.

```sql
CREATE PROCEDURE Login @user_name varchar(20),
                        @password varchar(20)
AS
    DECLARE @query varchar(250)
    SET @query = 'SELECT 1 FROM usertable WHERE username = ' + @username + ' AND password = ' @password
    EXEC(@query)
    
    GO
```

If the attacker enters the following inputs in the application input fields using the above stored procedure he will be able to login with any password:

User input: anyusername or 1=1' anypassword

#### illegal - logically incorrect query

For example, to find the column name, an attacker may give the following malicious input:

Username: 'Bob"

The resultant query will be

```sql
SELECT * 
FROM Users 
WHERE UserName= 'Bob"' 
AND password =
```

the db may return the following error message:

Incorrect Syntax near 'Bob'. Unclosed quotation mark after the character string " AND password='xxx".

#### union

An attacker uses a UNION clause to append a malicious query to the requested query.

The attacker checks for the UNION SQL injection vulnerability by adding a single quote character (') to the end of a "php?id=" command (QueryString).

The type of errore message received will tell the attacker if the db is vulnerable to a UNION SQL injection

```sql
-- original query
SELECT name, phone, address
FROM Users
WHERE Id=$id

-- if you set the Id value as:
$id=1 UNION ALL SELECT creditCardNumber,1,1 FROM CreditCardTable

-- the final query is:
SELECT name, phone, address
FROM Users
WHERE Id=1 UNION ALL SELECT creditCardNumber,1,1 FROM CreditCardTable
```

#### tautology

An attacker uses a conditional OR clause such that the condition of the WHERE clause will always be true

```sql
SELECT *
FROM users
WHERE name = '' OR '1'='1';
```

This query will always be true, as the second part of OR clause is always true

#### end of line comment

An attacker uses line comments in specific injection inputs.
The db will execute the code until it reaches the commented portion, after which it will ignore the rest of the query.

```sql
-- you can login to an admin account without the password
SELECT *
FROM members
WHERE username = 'admin'--' AND password = 'password'
```

#### in-line comments

This type of injections allows an attacker to bypass blacklisting, remove spaces, obfuscate, and determine database versions.

```sql
INSERT INTO Users (UserName, isAdmin, Password)
VALUES ('".$username."', 0, '".$password."')"
```

The attacker may provide malicious inputs as follows

UserName = Attacker', 1 /*
Password = */'mypwd

The generated query gives the attacker administrator privileges

```sql
INSERT INTO Users (UserName, isAdmin, Password)
VALUES ('Attacker', 1, /*', 0, '*/'mypwd')
```

#### piggybacked query (stacked queries)

An attacker injects an additional malicious query into the original query.

Attackers use a semicolon (;) as a query delimiter to separata the queries.

```sql
-- original query
SELECT *
FROM EMP
WHERE EMP.EID = 1001 AND EMP.ENAME = 'Bob'

-- the attacker concatenates the delimiter and malicious query

...;
DROP TABLE DEPT;
```

### Blind - inferential

The attacker has no error messages from the system to work on. He simply sends a malicious SQL query to the db.

### Out-of-band

Attackers use different communication channels to perform the attack and obtain the results.

