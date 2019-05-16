#使用docker容器运行MongoDB

#下载MongoDB的官方docker镜像

docker pull mongo:4

#查看下载的镜像

docker images

#启动一个MongoDB服务器容器

docker run --name mymongo -v /mymongo/data:/data/db -d -p 27017:27017 mongo:4

其中 -v /mymongo/data:/data/db --> 挂载数据目录

#查看docker容器状态

docker ps

#查看数据库服务器日志

docker logs mymongo



#Mongo Express是一个基于网络的MongoDB数据库管理界面

#下载mongo-express镜像

docker pull mongo-express

#运行mongo-express

docker run --link mymongo:mongo -d -p 27018:8081 mongo-express

-p ip:hostport:containerport



#mongo shell是用来操作MongoDB的javascript客户端界面