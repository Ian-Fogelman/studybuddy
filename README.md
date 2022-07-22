# studybuddy
### SETUP MYSQL INSTANCE
```
powershell
cd myworkingdir
docker pull mysql
docker run -d --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=secret -e MYSQL_DATABASE=mySchema mysql:latest
```
### PERMISSIONS AND SCHEMA
``` sql
USE mySchema;

ALTER USER 'root' IDENTIFIED WITH mysql_native_password BY 'secret';
flush privileges;

CREATE TABLE Fact
(id int primary key,
fact varchar(8000)
);

INSERT INTO fact
values(1,'Flows can be scheduled in salesforce')
# username:root password:secret
```
### SETUP LOOPBACK APP
```
lb4 app studybuddy
cd studybuddy
lb4 model
lb4 datasource
lb4 repository
lb4 controller
```
[![LoopBack](https://github.com/strongloop/loopback-next/raw/master/docs/site/imgs/branding/Powered-by-LoopBack-Badge-(blue)-@2x.png)](http://loopback.io/)
