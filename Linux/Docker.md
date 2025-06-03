[[Docker React]]
Run MySQL container
``` Bash
$ docker run -d -p 33060:3306 --name mysql-db -e MYSQL_ROOT_PASSWORD=secret mysql

###

#Copy file into docker
docker cp 01-create-user.sql 4d1:/01-create-user-.sql

source file.sql
```

```
$ docker exec -it [container-id] /bin/bash
$ mysql -u root -p
$ show databases;
$ use [your_database_name];
$ show tables;
```

### Run container on same network for debugging
``
``` Bash
docker run --rm -it --network container:mysql-db debian bash

apt update && apt install net-tools -y
netstat -tlnp



```

###  Run command inside mysql
`mysql -u root -p -e "SHOW VARIABLES LIKE 'bind_address';"`
### Commands if cannot connect to DB
`lsof -iTCP -sTCP:LISTEN -P | grep 33060`

 `ss -tuln | grep 3306`
