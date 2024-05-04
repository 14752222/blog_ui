# Apache使用


#### 安装

```Shell
    yum install -y httpd

```


#### 启用Apache
```Shell
systemctl start httpd

```

##### 查看服务状态
```Shell
systemctl status httpd.service
```

##### 重启服务应用 

```Shell        
sudo systemctl restart httpd
```


##### 关闭服务
```Shell
systemctl stop httpd
```
