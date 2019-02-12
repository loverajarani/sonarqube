# sonarqube
```
mysql -h <RDS_Instance_endpoint> -P 3306 -u <DB_USER_NAME> -p 

CREATE DATABASE sonarqube CHARACTER SET utf8 COLLATE utf8_general_ci;
CREATE USER sonarqube@localhost IDENTIFIED BY 'sonardb123';
CREATE USER sonarqube@'%' IDENTIFIED BY 'sonardb123';
GRANT ALL ON sonarqube.* TO sonarqube@localhost;
GRANT ALL ON sonarqube.* TO sonarqube@'%';
FLUSH PRIVILEGES;
show databases;
SELECT User FROM mysql.user;
quit


******** locally user creation *****************************************

useradd sonar
groupadd sonar
useradd -c "Sonar System User" -d /opt/sonar -g sonar -s /bin/bash sonar
chown -R sonar:sonar /opt/sonar
su sonar
cd /opt/sonar/bin/linux-x86-64/
./sonar.sh start
