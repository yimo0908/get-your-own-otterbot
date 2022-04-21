# OICQ

1. 下载安装 [nodejs](https://nodejs.org/)

2. 新建一个文件夹(以英文命名, eg. `tata`)，在该目录下打开cmd或powershell，运行指令`npm i oicq@1`

3. 运行指令`oicq 123456789 `(数字是你的bot账号)

4. 从獭窝中下载配置文件并放到上一步指定的目录（通常为`C:\Users\username\.oicq`）下（客户端选择`OICQ`）。

<details><summary>或根据注释及实际情况更改config.js（只需要在意带注释的字段，其余字段请不要更改）</summary>

```javascript
"use strict";
// 此文件必须名为config.js才能生效哦

module.exports = {

    //通用配置
    general: {
        platform:           1,       //1:安卓手机 2:aPad 3:安卓手表 4:MacOS 5:iPad
        log_level:          "info",  //日志等级，可选：trace,debug,info,warn,error,mark
        use_cqhttp_notice:  false,
    
        host:               "0.0.0.0",
        port:               5700,
        use_http:           false,
        use_ws:             false,
        access_token:       "",         //访问密钥, 即申请獭獭时的token
        secret:             "",         //访问密钥, 即申请獭獭时的token
        post_timeout:       30,
        post_message_format:"array",
        enable_cors:        false,      
        enable_heartbeat:   false,      //是否启用心跳
        heartbeat_interval: 15000,      //心跳间隔(毫秒)
        rate_limit_interval:500,        
        event_filter:       "", 
        post_url: [ 
            
        ],
        ws_reverse_url: [ // 
        // 獭窝反向WS Universal 地址
        ],
        ws_reverse_reconnect_interval: 3000, 
        ws_reverse_reconnect_on_code_1000: true, 
    },
    
    //每个账号的单独配置(用于覆盖通用配置) ← 通常无视，除非你有多个号使用这一客户端
    147258369: {
    
    },
};

```

</details>


   5. 在原目录下运行cmd/powshell, 重新运行指令 `oicq 123456789` (数字是你的bot账号)即可登录

   （ps.只有第一次登录需要输入密码/扫码）



`node i`命令卡住可能是连接不上国外服务器，在最后面加上` --registry https://registry.npm.taobao.org`即可

