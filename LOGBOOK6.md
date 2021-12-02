## Task 1

As you can see in the screen shot, by including a sequence of %s in our file, we were able to crash the program. This happened because printf will interpret every %s as a pointer to a string. Eventually it will try to access an invalid adress which will make the program crash.

[Logbook 6 - Task 1](/screenshots/logbook6-task1.png)

## Task 2a

We adapted the python script that was provided to print a series of %x. It wasn't until the 64th print, that we got our 4 byte number, which was 0x11141114.

[Logbook 6 - Task 2a](/screenshots/logbook6-task2a.png)

## Task 2b

Now that we know where our number was stored, we can replace it with the secret message's address and print out it's value. To do that we printed the %x format specifier 63 times and on the 64th time we printed out the %s format specifier, to print the string contained in that address.

[Logbook 6 - Task 2b - Part 1](/screenshots/logbook6-task2b-1.png)

[Logbook 6 - Task 2b - Part 2](/screenshots/logbook6-task2b-1.png)

## Task 3a

In order to change the value of the target variable, we will take advantage of the %n format specifier, that writes in a pointed location the number of characters printed until then. To do this, first we set our first 4 bytes to be the address of the target variable, in our case it was 0x080e5068. Then, since we know we need 64 %x format specifiers to access that value, we add those to the format string, followed by the %n format specifier. This way we were able to change the target variable's value (see screenshot).

[Logbook 6 - Task 3a](/screenshots/logbook6-task3a.png)

## Task 3b

In order to change the target variable's value to 0x5000, we need to add padding to the last %x format specifier. So, first we subtract the previously obtained target variable's value, that is now altered to be, in our case, 0x23c from 0x5000, which gives us 0x4dc4 (0x5000-0x23=0x4dc4). To recap, we set the first 4 bytes to be the address of the target variable, then we add 63 %x format specifiers to the string, and this time, the 64th %x will have a padding of 0x4dc4+8 (we need to add 8 because that format specifier was already printing an 8 bytes long string). In decimal value this translates to the following specifier %19916x. After running our altered code we get the intended result (see screenshots).

[Logbook 6 - Task 3b](/screenshots/logbook6-task3b.png)
