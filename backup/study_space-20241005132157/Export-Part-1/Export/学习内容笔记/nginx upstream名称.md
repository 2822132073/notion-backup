# nginx upstream名称

## nginx upstream名称

upstream的名字不可以只包含数字以及_，最好使用英文以及_和数字进行命名！！！！！

可能会出现nginx识别到指定的upstream，也可以将请求发送给后端，但是却报400 Bad Request错误。

> nginx配置
> 

```bash
 
location = /chat/config.json {
   proxy_pass http://23_18080;
   proxy_http_version 1.1;
   rewrite ^/chat/config.json /config.json break;
}
upstream 23_18080 { 
   server 192.168.165.23:18080;
}
```

> 现象
> 

```bash
[root@ng-22 conf.d]# curl 127.0.0.1:8000/chat/config.json
<!doctype html><html lang="en"><head><title>HTTP Status 400 – Bad Request</title><style type="text/css">h1 {font-family:Tahoma,Arial,sans-serif;color:white;background-color:#525D76;font-size:22px;} h2 {font-family:Tahoma,Arial,sans-serif;color:white;background-color:#525D76;font-size:16px;} h3 {font-family:Tahoma,Arial,sans-serif;color:white;background-color:#525D76;font-size:14px;} body {font-family:Tahoma,Arial,sans-serif;color:black;background-color:white;} b {font-family:Tahoma,Arial,sans-serif;color:white;background-color:#525D76;} p {font-family:Tahoma,Arial,sans-serif;background:white;color:black;font-size:12px;} a {color:black;} a.name {color:black;} .line {height:1px;background-color:#525D76;border:none;}</style></head><body><h1>HTTP Status 400 – Bad Request</h1></body></html>[root@ng-22 conf.nginx -s reload                                                                               
Your system is not activated. Please activate as soon as possible for normal use.     
[root@ng-22 conf.d]# curl 192.168.165.23:18080/chat/config.json
0020d7a1d0d70202a0d0225383e203e2132202a322e6f6963727566722020.......
```

> 日志
> 

```bash
183.94.133.245 - - [27/Sep/2024:18:56:36 +0800] "GET /config.json HTTP/1.1" 200 16318 "-" "Ktor client" "-" port:"18080"
192.168.165.22 - - [27/Sep/2024:18:57:26 +0800] "GET /config.json HTTP/1.1" 400 800 "-" "curl/7.71.1" "-" port:"18080"
```

> 更新为这个名字就可以了
> 

```bash
upstream chatServer {
  server 192.168.165.23:18080;
}
```