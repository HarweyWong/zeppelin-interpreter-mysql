# zeppelin-interpreter-mysql
Mysql Interpreter for Zeppelin 0.5.0-incubating

## build
```
git clone https://github.com/jiekechoo/zeppelin-interpreter-mysql
mvn clean package
```

## deploy

```
mkdir /opt/zeppelin/interpreter/mysql
cp target/zeppelin-mysql-0.5.0-incubating.jar /opt/zeppelin/interpreter/mysql
# copy dependencies to mysql directory
cp mysql-connector-java-5.1.6.jar log4j-1.2.17.jar slf4j-api-1.7.10.jar slf4j-log4j12-1.7.10.jar commons-exec-1.1.jar /opt/zeppelin/interpreter/mysql
bin/zeppelin-daemon.sh restart
```

## using

In Zeppelin WEBUI http://192.168.1.230:8080, Create new note
```
Click Settings, Save it.
```

```
%mysql

SELECT type, COUNT(1) c FROM Syslog.Users Group By type Order By c DESC;

RUN IT
```
