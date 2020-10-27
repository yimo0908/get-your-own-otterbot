# cqhttp-go

1.先请自行下载 [go-cqhttp](https://github.com/Mrs4s/go-cqhttp/releases)

2.新建一个文件夹(以英文命名, eg. tata)，将`go-cqhttp.exe`放入其中并运行，使其自动生成框架相关文件和文件夹，然后关闭`go-cqhttp`，编辑`config.json`


`"uin"`: QQ账号  
`"password"`: "QQ密码"  
`"access_token"`: "獭獭のtoken"  
`"post_urls"`: {"塔塔露のurl": ""}  
`"reverse_url"`: "獭窝のws地址"

>```json 
>{
>	"uin": ,
>	"password": "",
>	"encrypt_password": false,
>	"password_encrypted": "",
>	"enable_db": true,
>	"access_token": "",
>	"relogin": true,
>	"relogin_delay": 3,
>	"http_config": {
>		"enabled": true,
>		"host": "0.0.0.0",
>		"port": 5700,
>		"timeout": 0,
>		"post_urls": {"": ""},
>		"post_message_format": "string"
>	},
>	"ws_config": {
>		"enabled": false,
>		"host": "0.0.0.0",
>		"port": 6700
>	},
>	"ws_reverse_servers": [
>		{
>			"enabled": true,
>			"reverse_url": "",
>			"reverse_api_url": "",
>			"reverse_event_url": "",
>			"reverse_reconnect_interval": 3000
>		}
>	],
>	"debug": false
>}
>```



3.保存后启动`go-cqhttp.exe`即可。