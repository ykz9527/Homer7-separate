Homer7分离服务后部署注意事项
========
#### 部署说明
一共三个文件夹,每个文件夹都是一个服务,如果想要在机器上部署三个服务里的某个服务,根据下面的提示进入相应的文件夹执行make命令即可

#### 拉取文件后运行
```bash
make init
```
#### 之后每次运行
```bash
make run
```
#### 停止服务
```bash
make stop
```

相关信息:
* 数据库
  * 用户名:postgres
  * 密码:homerSeven
  * 端口:5432
  
* 登录
  * 登录端口号:8002
  * 用户名:admin
  * 密码:sipcapture
  
* hep消息接收端口:9060
