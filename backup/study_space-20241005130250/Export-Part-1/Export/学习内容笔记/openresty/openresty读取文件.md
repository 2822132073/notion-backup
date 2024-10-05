# openresty读取文件

在openresty中读取文件，然后进行处理，需要像以下这么处理

```lua
function read_file(file_name)
    if not file_name then
        return nil,"file_name not assign!!"
    end
    local file = io.open(file_name,'r')
    if not file then
        ngx.say("read file error")
        return      
    end         
    local data =  file:read('*all')
    file:close()
    return data,nil
end
local content,err = read_file('/etc/config.json')
if not content then
    ngx.say(err)
end
ngx.say(content)
```

> nginx配置文件
> 

```lua
lua_code_cache off;
server {
    listen 9000;
    location /config.json{
        content_by_lua_file /usr/local/openresty/nginx/conf/conf.d/lua/encrypt_file.lua;
    }
}
```

> 结果
> 

```lua
[root@nginx /usr/local/openresty/nginx/conf/conf.d]# curl 127.0.0.1:9000/config.json
{
"name":"fsl",
"age":18
}

```