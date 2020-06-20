### 购买 按流量计费 腾讯云 CentOS 服务器 部署node：
不可以解析域名

1.下载最新的稳定版 v11.10.0 到本地
>wget https://nodejs.org/dist/v11.15.0/node-v11.15.0-linux-x64.tar.xz 

2.下载完成后, 将其解压
>tar xvJf node-v11.15.0-linux-x64.tar.xz 

3.将解压的 Node.js 目录移动到 /usr/local 目录下
>mv node-v11.15.0-linux-x64 /usr/local/node-v11

4.配置 node 软链接到 /bin 目录
>ln -s /usr/local/node-v11/bin/node /bin/node

5.配置 npm
>ln -s /usr/local/node-v11/bin/npm /bin/npm

配置 npx
>ln -s /usr/local/node-v11/bin/npx /bin/npx


6.配置环境变量
>echo 'export PATH=/usr/local/node-v11/bin:$PATH' >> /etc/profile

7.生效环境变量
>source /etc/profile





8.通过 npm 安装进程管理模块 pm2
>npm install pm2 --global


9.使用 PM2 来启动 HTTP 服务
原来启动服务器的方式：
>node server.js
使用pm2启动服务器的方式：
>pm2 start server.js

10.查看日志，可以使用
>pm2 logs

11.查看进程
>pm2 ls


12.关闭进程
>pm2 delete <name>





### 购买 包年包月 腾讯云 CentOS 服务器 部署node：
可以解析域名

1.包年包月服务器执行如上操作后，需购买域名。

2.购买域名购买完成后, 需要将域名解析到实验云主机上
域名设置解析后需要过一段时间才会生效，通过 ping 命令检查域名是否生效，如：
>ping www.yourmpdomain.com


3.申请 SSL 证书
腾讯云提供了 SSL 证书的免费申请:https://console.qcloud.com/ssl?_ga=1.176221794.632074309.1549847300
可以到 SSL 控制台下载您的证书文件

4.搭建 HTTPS 服务
安装 Nginx:
>yum install nginx -y

启动 Nginx：
>nginx
(>nginx -s reload //命令重启 Nginx)

配置 HTTPS 反向代理:
外网用户访问服务器的 Web 服务由 Nginx 提供，Nginx 需要配置反向代理才能使得 Web 服务转发到本地的 Node 服务。
先将之前下载的 SSL 证书(解压后 Nginx 目录分别以 crt 和 key 作为后缀的文件)上传到/etc/nginx目录的服务器上
Nginx 配置目录在 /etc/nginx/conf.d，我们在该目录创建 ssl.conf
示例代码：/etc/nginx/conf.d/ssl.conf:
```
server {
	listen 443;
	server_name www.example.com; # 改为绑定证书的域名
	# ssl 配置
	ssl on;
	ssl_certificate 1_www.example.com_bundle.crt; # 改为自己申请得到的 crt 文件的名称
	ssl_certificate_key 2_www.example.com.key; # 改为自己申请得到的 key 文件的名称
	ssl_session_timeout 5m;
	ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
	ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:HIGH:!aNULL:!MD5:!RC4:!DHE;
	ssl_prefer_server_ciphers on;
	location / {
		proxy_pass http://127.0.0.1:8765;
	}
}
```
让 Nginx 重新加载配置使其生效：
>nginx -s reload 





### 在云服务器上配置mongoDB：

1.安装MongoDB及其客户端命令行工具
>yum install mongodb-server mongodb -y
查看版本：
>mongod --version
>mongo --version

2.创建目录，用于 MongoDB 数据和日志存储
>mkdir -p /data/mongodb
>mkdir -p /data/logs/mongodb

3.启动 MongoDB
>mongod --fork --dbpath /data/mongodb --logpath /data/logs/mongodb/weapp.log

4.检查是否启动成功(MongoDB首次启动时间较长)
>netstat -ltp | grep 27017


查找文件
find / -name <名字>


