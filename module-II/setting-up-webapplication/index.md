# setting up local web-application server

# 1 : setting up LAMP stack

LAMP stack is stands for: 

* Linux
* Apache (apache2)
* MySQL	(db)
* Php 	(scripting Lang.)

---

# 2 : download the web-application code.

you can download the code from this [GitHub Repo](https://github.com/anir0y/arishti-01)

# 3 : configuration

## MySql

```sql

# create user with password

CREATE USER 'dbadmin'@localhost IDENTIFIED BY 'dbadmin@123';

# create db:

CREATE DATABASE IF NOT EXISTS 'users' DEFAULT CHARACTER SET latin1 COLLATE latin1_swedish_ci;

# select DB

use `users`;

# grant our user privileges

GRANT ALL PRIVILEGES ON user.* to 'dbadmin'@'localhost'

# creating tables:

CREATE TABLE IF NOT EXISTS `userlogin` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `username` varchar(200) NOT NULL,
  `password` varchar(33) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB  DEFAULT CHARSET=latin1 AUTO_INCREMENT=1 ;

# insert values:

INSERT INTO `userlogin` (`id`, `username`, `password`)VALUES (99, 'mentor', 'a1857b83457cfef98da22fefa2fdd3ba');
INSERT INTO `userlogin` (`id`, `username`, `password`)VALUES (1, 'admin', 'a1857b83457cfef98da22fefa2fdd3ba');
```

### PHP

* open `dbconf.php` add the creds:

````php
# old
new mysqli("127.0.0.1", "useradm", "useradm", "userdb")

# new
new mysqli("127.0.0.1", "dbadmin", "dbadmin", "users")

```
