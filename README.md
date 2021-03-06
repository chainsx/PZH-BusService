# 花城智慧公交 WebApplication

## 简介

> 感谢 [dtsdao](https://github.com/dtadao) 所写的工具，感谢他提供的源码

遵循 GPL v3.0 协议公开源码

使用海信提供给攀枝花公交公司的API来获取公交实时到站信息

主体程序为HTML文件，Python 脚本充当一个代理服务器提供API的访问权限，避免跨域问题

使用 [MDUI](https://www.mdui.org/) v0.4.2 作为前端库，遵守 Material Design 设计规范

## 使用说明

1. 首先需要有一台正在运行的服务器
   
   环境要求安装 Python 3.4 及以上

   需要互联网连接

2. 使用 Git clone本项目到服务器的某个地方
   
   或者你也可以下载release里的压缩HTML后的压缩包，然后自行解压

3. 更改 `server.py` 中 `constConf` 的相关值
   
   - `servAdd` 为远端API地址
   - `locAdd` 为你想绑定的本地地址（支持域名）
   - `locPort` 为你想绑定的本地端口

4. 使用 `python3 server.py` 运行代理服务器

5. 打开浏览器访问你设置的 `locAdd` 和 `locPort` 就可以看到HTML页面

## 构建deb安装包

1. 使用`dpkg-buildpackage`构建软件包

2. `pzhbluebus`运行

3. `server.py`的绝对路径为`/usr/share/pzhbluebus/server.py`

## 注意事项

1. 推荐通过nginx进行优化，如果想用https必须配置nginx
   
   方法为nginx代理到python脚本监听的端口就可以，网上有教程

2. 域名需要提前解析到本机ip，不然会报错
3. 如果想关掉终端也可以运行，Linux 可以使用 `nohup` 或 `screen`，Windows 大概远程桌面不关掉会话就行
