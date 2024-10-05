# map的使用实验

[nginx(二十四)map指令_nginx map-CSDN博客](https://blog.csdn.net/wzj_110/article/details/123747380)

[Module ngx_stream_map_module](https://nginx.org/en/docs/stream/ngx_stream_map_module.html)

之前在工作中为了安全，经常对后端接口代理进行一一映射，有时候接口太多，就特别麻烦，而且配置文件太长可能有时候自己都不知道自己配置的是什么，所以就想用nginx的 `map` 指令，map可以将，一个和多个已有的指令，去匹配一个字典，然后再生成新的变量

```bash
map $remote_addr $limit {
    127.0.0.1    "";
    default      $binary_remote_addr;
}
```

这是官方给的一个示例，可以通过$remote_addr，然后指定一些一一映射的值，然后就可以生成一个新的变量。这个映射的部分分为两个部分：

- 源值：可以是字符串或者是正则表达式，使用正则需要在开头加上 `~` 或者 `~*` ，前者区分大小写，后者不区分。
- 目标值：根据源值获得。

> 如果 `$remote_addr` 匹配多个源值，那么会优先级来得出结果，这个优先级在这里
> 
> 1. string value without a mask
> 2. longest string value with a prefix mask, e.g. “`.example.com`”
> 3. longest string value with a suffix mask, e.g. “`mail.*`”
> 4. first matching regular expression (in order of appearance in a configuration file)
> 5. default value

## 具体示例

> 具体的内容， `location /` 是所有没有匹配到的uri前往的地方，所以我们在这里做处理，如果我么还有一些其他的uri需要特殊处理，还是可以继续写的。
> 

```bash
map $uri $backend{
    default '';
    /api/chat/getUserInfo "chatServer";
    /api/chat/sendByAjax "chatServer";
    /api/chat/recoverBatchRemind  "chatServer";
    /api/chat/getRemindCount  "chatServer";
    /api/ai/chat "AiServer";
    ~/api/ai/post.* "AiServer";
    /api/application/get "EsServer";
    ~/api/application/.* "EsServer";
}

server {
   listen 80;
   location / {
      if ($backend = '') {
          echo '404';
      }
      proxy_pass http://$backend;
   }

}

```

```bash
upstream chatServer{
   server 127.0.0.1:8001;
}
upstream AiServer {
   server 127.0.0.1:8002;
}
upstream EsServer{
   server 127.0.0.1:8003;
}

```

```bash
server {
    listen 8001;
    location / {
      echo "chatServer: $uri";
    }
}
server {
    listen 8002;
    location / {
      echo "EsServer: $uri";
    }
}
server {
    listen 8003;
    location / {
      echo "AiServer: $uri";
    }
}
```

## 效果

> 在使用时，请注意在使用纯字符匹配时，不管是变量名，还是变量值的匹配，都不区分大小写。正则模式则是可以开启大小写敏感。你可以在你向区分大小写的地方的字符前加上正则的标识，而不使用。
> 

```bash
[root@nginx /usr/local/openresty/nginx/conf/conf.d]# curl 127.0.0.1/api/application/get
AiServer: /api/application/get
[root@nginx /usr/local/openresty/nginx/conf/conf.d]# curl 127.0.0.1/api/application/GET
AiServer: /api/application/GET
[root@nginx /usr/local/openresty/nginx/conf/conf.d]# curl 127.0.0.1/api/application/Get
AiServer: /api/application/Get
[root@nginx /usr/local/openresty/nginx/conf/conf.d]# curl 127.0.0.1/api/ai/Post
404
[root@nginx /usr/local/openresty/nginx/conf/conf.d]# curl 127.0.0.1/api/ai/post
EsServer: /api/ai/post
```