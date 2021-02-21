# Find Saved Chrome Passwords Using Python
In this python program we are going to crack and get in Google Chrome database passwords. What that means is if Google Chrome has saved passwords for logging into Facebook, Twitter, Instagram or anything else, what this program will do is it will get the passwords from the Chrome and  you'll have URL, username and passwords to all the saved details.

## To get started, let's install required libraries:
> pip3 install pycryptodome pypiwin32

## Approach:

Chrome saves passwords locally in a SQLite database. So,

- First, we get the encryption key using **get_encryption_key()** function.
- Then we **copy the SQLite database** (located at "%USERPROFILE%\AppData\Local\Google\Chrome\User Data\default\Login Data") that has the saved passwords to the current directory and connects to it, this is because the original database file will be locked when Chrome is currently running.
- After that, we make a **select query to logins table and iterate** over all login rows, we also **decrypt each password** and reformat the date_created and date_last_used date times to more human readable format.
- Finally, we **print the credentials** and remove the database copy from the current directory.


#### As chrome changed its encryption after Chrome 80 so the Version_lower80.py will run only with lower versions. But Version_above80 will run with Versions>=Chrome 80
