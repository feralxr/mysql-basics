net stop mysql80
stops already running server

mysqld --shared-memory --skip-grant-tables
enables unauth mode

to create new user:
FLUSH PRIVILEGES;

CREATE USER 'ayush'@'localhost' IDENTIFIED BY 'your_new_password';
GRANT ALL PRIVILEGES ON *.* TO 'ayush'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;


or change pass of existing
ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_secure_password';
FLUSH PRIVILEGES;


stop the already running server and restart
net start mysql80

so see existing users
SELECT user, host FROM mysql.user;
