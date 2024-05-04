# Nginx 使用

##### 安装nginx

- 安装步骤
  1、添加源 默认情况Centos7中无Nginx的源，最近发现Nginx官网提供了Centos的源地址。因此可以如下执行命令添加源：

```Shell
rpm -Uvh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
```

```Shell
yum install -y nginx

```

#### 启动并设置开机自动运行

```Shell
sudo systemctl start nginx
sudo systemctl enable nginx
```

##### 查看服务状态

```Shell
systemctl status nginx.service
```

##### 更新nginx配置 {id="nginx_1"}

```Shell
nginx -s reload
```

##### 重启服务应用 

```Shell  
sudo systemctl restart nginx
```

##### 关闭服务

```Shell
systemctl stop nginx
```