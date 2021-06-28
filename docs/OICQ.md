# OICQ

1. 下载安装 [nodejs](https://nodejs.org/)

2. 下载 [onebot](https://github.com/takayama-lily/onebot)的 源码包

   （点击[链接](https://codeload.github.com/takayama-lily/onebot/zip/master)下载，或者直接git clone）

3. 打开cmd/powershell，cd进对应目录(onebot)

4. 在目录下执行 `npm up` 安装依赖(今后也可使用此命令一键更新内核)

5. 在獭窝中下载`config.js`文件并放到目录下。

6. 在目录下运行cmd/powshell, 输入指令 `node main 123456789` (数字是你的bot账号)，回车

   （ps.只有第一次登录需要输入密码）

7. 想要缝合塔塔露只需要在post_url那里加上对应的塔塔露url就行
> ```javascript
> post_url: [
> 	“塔塔露的url”
> ],
> ```

  

#### 更改登录设备类型

在config.js中找到`platform`字段，修改其值即可更改登录设备类型


| 值   | 类型  | 登录状态 | 限制                                           |
| ---- | --------|----- | ---------------------------------------------- |
| 0    | Android Pad | 平板在线 | 无法接收 `group_notify` 事件、无法接收口令红包 |
| 1    | Android Phone| 手机在线 | 无                                             |

---



`node main xxxxxxxxx`与`npm up`命令卡住可能是连接不上国外服务器，在最后面加上` --registry https://registry.npm.taobao.org`即可