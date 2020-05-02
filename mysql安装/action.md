
#### 拉取 mysql镜像
```
docker pull mysql:5.7.23
```

#### 启动 mysql
```docker
docker run -d --name mysql \
           -v ~/mysql/data:/var/lib/mysql \
           -e MYSQL_ROOT_PASSWORD=123456 \
           -p 3306:3306 \
           mysql:5.7.23
```

#### 进入mysql，进行远程访问授权
```
docker exec -it mysql bash

mysql -uroot -p123456

GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT;
```

#### 远程访问OK