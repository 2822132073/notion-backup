# nginx跨域解决

[内容安全策略（CSP） - HTTP | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/CSP)

当前端访问资源跨域时，可以在nginx中添加请求头

`Content-Security-Policy`

除了上述提到的常见策略指令外，还有以下一些重要的`Content - Security - Policy`策略指令：

### 1. `style-src`

- **作用**：用于指定样式表资源（如CSS文件）可以从哪些源获取。
- **示例**：`style-src 'self' <https://cdn.example.com> 'unsafe-inline'`，表示样式表可以从当前网站自身、`https://cdn.example.com`获取，并且允许内联样式（`unsafe-inline`）。

### 2. `media-src`

- **作用**：定义媒体资源（如音频、视频文件）的来源。
- **示例**：`media-src 'self' <https://media.example.com>`，表示媒体资源可以从当前网站自身和`https://media.example.com`获取。

### 3. `connect-src`

- **作用**：指定哪些源可以进行连接请求，例如XMLHttpRequest、WebSocket等连接。
- **示例**：`connect-src 'self' <https://api.example.com`>，表示可以从当前网站自身和`https://api.example.com`进行连接请求。

### 4. `font-src`

- **作用**：确定字体资源的来源。
- **示例**：`font-src 'self' <https://fonts.example.com> data:`，表示字体可以从当前网站自身、`https://fonts.example.com`以及使用`data:`协议的源获取。

### 5. `frame-src`

- **作用**：规定框架（如`<iframe>`）资源可以从哪些源获取。
- **示例**：`frame-src 'self' <https://iframe.example.com`>，表示框架可以从当前网站自身和`https://iframe.example.com`获取。

### 6. `object-src`

- **作用**：用于指定对象资源（如`<object>`标签嵌入的资源）的来源。
- **示例**：`object-src 'none'`，表示禁止加载任何对象资源。

### 7. `sandbox`

- **作用**：将页面内容置于一个沙盒环境中，限制其对浏览器功能的使用。
- **示例**：`sandbox`（单独使用该指令会启用一些默认的限制），或者`sandbox = "allow - forms allow -scripts"`，可以根据需要指定允许的功能。

### 如果前端需要访问 `blob` 或者 `data` 数据，可以参考以下设置

```bash
add_header 'Content-Security-Policy' "img-src 'self' blob: data:;";
```

> 记住 `blob:` 和 `data:` 需要有空格，一定要注意到有空格
> 

### 如果同时需要有多个域名

```bash
add_header 'Content-Security-Policy' "img-src 'self' example1.com example2.com example3.com blob: data:;";
```