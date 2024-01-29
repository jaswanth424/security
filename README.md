# SpringBootSecurity
use car_db
mysql> show tables;
+------------------+
| Tables_in_car_db |
+------------------+
| Car              |
| UserInfo         |
+------------------+
2 rows in set (0.00 sec)

mysql> select * from UserInfo;
Empty set (0.01 sec)

curl --location 'http://localhost:8080/auth/addNewUser' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "one",
    "password": "cisco123",
    "email": "jk@gmail.com",
    "roles": "ROLE_USER"
}'

mysql> select * from UserInfo;
+----+--------------+------+--------------------------------------------------------------+-----------+
| id | email        | name | password                                                     | roles     |
+----+--------------+------+--------------------------------------------------------------+-----------+
|  1 | jk@gmail.com | one  | $2a$10$mrRMCHHoWX1/U5s7qgOU5uC0GvTelqTwugEmmWsEQ14/R8YE/3zJy | ROLE_USER |
+----+--------------+------+--------------------------------------------------------------+-----------+
1 row in set (0.00 sec)

mysql>


curl --location 'http://localhost:8080/auth/generateToken' \
--header 'Content-Type: application/json' \
--data '{
    "username":"one",
    "password":"cisco123"
}'


http://localhost:8080/auth/user/userProfile
