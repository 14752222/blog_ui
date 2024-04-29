# docker 容器导出MySQL

![image.png](image.png)

### 进入mysql容器

```shell
docker exec -it 容器名称/id bash
```

### 导出数据库

```shell
mysqldump -uroot -p密码 数据库名称 > 导出文件.sql
```

### 退出容器

```Shell
exit
```

### 将导出文件拷贝到宿主机

```shell
docker cp 容器名称:/导出文件.sql /宿主机路径
```





