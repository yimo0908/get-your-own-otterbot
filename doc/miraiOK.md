# miraiOK+cqhttp

### 搭建及配置

1)  首先请自行下载[miraiOK](https://github.com/LXY1226/MiraiOK#%E4%B8%8B%E8%BD%BD%E5%9C%B0%E5%9D%80), [cqhttp-mirai插件](https://github.com/yyuueexxiinngg/cqhttp-mirai/releases)  

2)  新建一个文件夹(以英文命名, eg. tata)，将`miraiOK.exe`放入其中并运行，使其自动生成框架相关文件和文件夹.

3) 关闭`miraiOK`，将`cqhttp-mirai.jar`放入`plugins`文件夹，再次启动`miraiOK.exe`，等到控制台提示登录后关闭.

4) 新建`.\plugins\CQHTTPMirai`文件夹，并配置`plugins\CQHTTPMirai\setting.yml`文件内容（2种方法）  
① 獭窝直接下载 
② 复制以下代码并更改`plugins\CQHTTPMirai\setting.yml`文件内容。 

>``` yaml
># 本文件只测试了主窝 食材村(笔窝) 风窝 鸡窝，其他窝不一定适用，请自行尝试
>debug: true
># Debug日志输出选项
>'1234567890':
># 要进行配置的QQ号
>cacheImage: true
># 是否缓存所有收到的图片
>heartbeat:
>enable: true
># 是否发送心跳包
>interval: 15000
># 心跳包发送间隔, 默认为 15000毫秒
>http:
>enable: false
>host: 0.0.0.0
>port: 5700
>accessToken: ""
>postUrl: ""
># 事件及数据上报URL,即塔塔露提供的url
>postMessageFormat: string
>secret: ""
>ws_reverse:
>   - enable: true 
>     # 可选，是否启用反向客户端,即是否启用獭獭
>     postMessageFormat: string
>     reverseHost: 
>     # 主窝 xn--v9x.net
>     # 食材村（笔窝）bot.pencilss.top
>     # 风窝 temp.dead-war.cn
>     # 鸡窝 tata.guomie.club
>     reversePort: 
>     # 主窝、食材村(笔窝)和鸡窝填80，风窝填8002
>     reversePath: /ws
>     useUniversal: true
>     reconnectInterval: 3000
>     accessToken: ""
>     # 访问口令，獭窝申请的时候的token
># 本文件只测试了主窝 食材村(笔窝) 风窝 鸡窝，其他窝不一定适用，请自行尝试
>```

5)  保存后启动`miraiOK.exe`，控制台出现登录提示后，在控制台输入

>login QQ账号 QQ密码

并回车，进行登录即可。  
————→若配置并登录成功，则会在控制台出现以下信息。

```
[DEBUG] [CQHTTPMirai] Host: bot.pencilss.top, Port: 80, Enable: true, Use Universal: true
[DEBUG] [CQHTTPMirai] bot.pencilss.top:80-Client-Universal 开始启动
[DEBUG] [CQHTTPMirai] bot.pencilss.top:80-Client-Universal Websocket Client启动完毕
```

信息根据窝的不同，会有差异。



### 自动登录

自行更改`\config\Console`文件夹里的`AutoLogin.yml`

`123456654321`替换为qq号，`example`替换为qq密码

>```yaml
>plainPasswords: 
>	123456654321: example
>md5Passwords: 
>	123456654321: 1A 79 A4 D6 0D E6 71 8E 8E 5B 32 6E 33 8A E5 33
>```