视频互通（网页版）
---

### 本机联调

不启服务：浏览器直接开两个index.html页

或

启http服务：`live-server . --port=端口`

### 内网联调

```
npm install live-server -g
openssl req -newkey rsa:2048 -new -nodes -x509 -days 3650 -keyout key.pem -out cert.pem
live-server . --https=./config.js --port=端口 --host=内网ip
```
启https服务，config.js是https的配置模块

live-server 
>https://www.npmjs.com/package/live-server

### 登陆

- App ID
- Channel
- Token

从声网开发者中心(https://docs.agora.io/en)获取。双端对等输入即可互通
