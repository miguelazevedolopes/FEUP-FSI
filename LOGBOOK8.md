## Task 1

As suggested we got familiar with the database in question

[Logbook 8 - Task 1](/screenshots/logbook8-task1.png)
[Logbook 8 - Task 1 - Full Table](/screenshots/logbook8-task1extra.png)

## Task 2.1

We found two possible routes to gain access to the admin account.

The first one was to input the following username: 
```admin' OR ''=' ```

By adding the OR statement, we make the password verification irrelevant because the first condition is met.

Another way to gain access is by commenting the password verification:

```admin';#```

The # is the symbol for a line comment in PHP and therefore, everything after the semicolon will be ignored (including the password verification).

The proof of access screenshots are included below.

[Logbook 8 - Task 2.1](/screenshots/logbook8-task2-1.png)

## Task 2.2

To repeat the process described earlier in the terminal we used the following command:

```curl 'www.seed-server.com/unsafe_home.php?username=admin%27%20or%20%27%27=%27&Password=11'```

Here we used a password value of 11, but as stated earlier, that value is irrelevant.

[Logbook 8 - Task 2.2](/screenshots/logbook8-task2-2.png)

## Task 2.3

What we were asked to do in this task is called Stacking Queries, however query stacking does not work in every situation. Most of the time, this kind of attack is impossible because the API and/or database engine do not support this functionality. In our particular case (PHP with MySQL) this exploit isn't possible.

## Task 3.1

In order to change the admin's salary we used injection to add an extra line to the UPDATE query (see screenshot):

```', salary='9999999```

[Logbook 8 - Task 3.1](/screenshots/logbook8-task3-1.png)
[Logbook 8 - Task 3.1 - Changed Salary](/screenshots/logbook8-task3-1extra.png)

## Task 3.2

To change other people's salary we needed to ignore the ID verification. So, we repeated the commenting technique from earlier and injected the following piece of code, which changes Boby's salary to 1:

```', salary='1' where name='Boby';#```

[Logbook 8 - Task 3.2](/screenshots/logbook8-task3-2.png)