这是一个(wd-server)[https://github.com/wheasy/wd-server]示例站点。

### 启动服务

假设站点根目录位于  `~/project/site`

在站点根目录启动

```
$ cd ~/project/site
$ wd-server
```

在任意位置启动站点，并指定`端口号`

```
$ wd-server -d ~/project/site -p 8080
```

>如端口号被占用，wd-server 会自动尝试在原端口上加1后启动。

### 目录结构
wd-server有三个特殊文件（夹）

名称|说明
----|----
blocks|  模板存放目录
cssLib|    LESS文件存放目录
.wdsvr   |可通过该文件配置wd-server

wd-server 默认不会显示这三个文件

### 发布
你可以通过 `wd-server build`发布站点，发布后不包括 `block`和`less`文件。

默认会发布到站点根目录的 `_build`目录，也可通过参数 `r`指定目录。

`wd-server build [d] [r]`

* d 站点根目录
* r 要发布的目录，相对路径或绝对路径

```
$ wd-server build -d ~/project/site -r ~/project/site-build
```

###.wdsvr 详解

改文件位于站点根目录，JSON格式，可通过它配置服务。

>默认端口号为8180
>
>wd-server 内置了常见mime，需要补充时，可通过mime添加

```
{
    // 端口号
    "port": 8180,
    // 忽略文件，目录索引和发布时会忽略以下文件
    "ignore": [
        ".DS_Store", 
        "blocks", 
        "less", 
        ".git", 
        ".svn", 
        ".npm", 
        "server.sh", 
        "server.bat"
    ],
    mime:{
        "html": "text/html"
        ......
    }
}
```

如需要指定端口号，可在启动时通过参数`p`指定。

### 答疑
如有疑问或建议，请在[这里](https://github.com/wheasy/wd-server/issues)上留言。或加入QQ群：370792320


<!--
##其他

如果`wd-server`不能满足你的需求，请不必沮丧，还有一个叫[Astros](#)的项目，除了`wd-server`的功能，还具备自支持模块化开发、自动合并JS依赖、自动合成雪碧图和字体文件等功能。

-->