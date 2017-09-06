Golang123   
=

golang123 是一个开源的社区系统。界面优雅，功能丰富，小巧迅速，
已在[golang中文社区](https://www.golang123.com) 得到应用，你完全可以用它来搭建自己的社区。       

golang123的技术架构是前后端分离的, 前端使用**vue**、**iview**、**node.js**、**nuxt**等技术来开发, 后端使用**go**、**gorm**、**iris**等技术来开发。golang123的技术选型也是超前的, 我们大胆得使用**nuxt**来做**前后端同构渲染**。    

*golang123目前正处于活跃的开发中，预计十月初发布Beta版*

## 🌅 项目截图
<img src="https://user-images.githubusercontent.com/2443162/30106321-a234dc0c-932d-11e7-8f66-020975158dcd.jpeg" width="1000" alt=""/>

## Golang123线上机器配置
| CPU | 1核     |  
|:---------|:-------:|
| **内存**     |  **512 MB** |
| **带宽**  |  **1Mbps** |
## 🚀 安装

### node.js
todo

### golang
todo

### mysql
todo

### redis
* [Linux下安装](https://www.golang123.com/topic/10)
* Windows下安装(todo)
* Mac下安装(todo)

### 前端依赖的模块
进入`golang123/website/`目录，输入命令

```
npm install
```

如果安装失败，或速度慢，可尝试阿里的镜像

```
npm install --registry=https://registry.npm.taobao.org
```

### 后端依赖的库

```
//iris web框架
go get -u github.com/kataras/iris

//gorm 持久层框架
go get -u github.com/jinzhu/gorm

//redis客户端工具
go get github.com/garyburd/redigo/redis

//uuid生成工具
go get github.com/satori/go.uuid

//防XSS攻击
go get -u github.com/microcosm-cc/bluemonday

//markdown解析器
go get github.com/russross/blackfriday
```

## ⚙️ 配置
### hosts   
127.0.0.1 dev.golang123.com  

### nginx 
1. 将`golang123/nginx/dev.golang123.com.conf`文件拷贝到nginx的虚拟主机目录下
2. 将`golang123/nginx/server.key`和`golang123/nginx/server.crt`拷贝到某个目录下
3. 打开nginx的虚拟主机目录下的`dev.golang123.com.conf`文件，然后修改访问日志和错误日志的路径，即access\_log和error\_log。
4. 修改证书路径为server.key和server.crt所在的路径，即ssl_certificate和ssl\_certificate\_key

请参考如下配置中`请修改`标记的地方:

```
server {
    listen 80;
    server_name dev.golang123.com;

    access_log /path/logs/golang123.access.log; #请修改
    error_log /path/logs/golang123.error.log;   #请修改

    rewrite ^(.*) https://$server_name$1 permanent;
}

server {
    listen       443;
    server_name dev.golang123.com;

    access_log /path/logs/golang123.access.log; #请修改
    error_log /path/logs/golang123.error.log;   #请修改

    ssl on;
    ssl_certificate /path/cert/golang123/server.crt;     #请修改
    ssl_certificate_key /path/cert/golang123/server.key; #请修改
    
    ...
    
}
```

### 前端配置
将`golang123/website/config/index.example.js`文件重命名为`index.js`

### 后端配置
即修改`golang123/website/config/index.js`文件中go字段下的配置  

1. 将`golang123/config.example.json`文件重命名为`config.json`
2. 打开`config.json`，修改mysql连接地址及端口
3. 修改redis的连接地址及端口
4. 修改图片上传的目录
5. 修改域名邮箱的用户名及密码(golang123使用的是QQ域名邮箱)

## ❓问题

有任何问题或建议都欢迎提 issue  

## 👥 技术交流  
qq群: 32550512 

## 💰 赞助
您可以通过扫描下图中的二维码来赞助我, 金额任意😃 
    
<img style="display:inline-block;vertical-align: top;" src="https://user-images.githubusercontent.com/2443162/30111902-10954434-9342-11e7-8e38-40ea8471c628.png" height="380" alt=""/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://user-images.githubusercontent.com/2443162/30106247-6b433842-932d-11e7-8f22-bc14a05ab427.png" height="400" alt=""/>



## License
[GPL](https://github.com/shen100/golang123-api/blob/master/LICENSE "")      
Copyright (c) 2013-present, shen100
