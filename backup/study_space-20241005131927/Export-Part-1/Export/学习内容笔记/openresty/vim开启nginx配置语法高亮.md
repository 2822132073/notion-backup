# vim开启nginx配置语法高亮

有时候我们通过二进制安装的nginx，vim打开时无法语法高亮，所以我们需要自己手动配置vim，使其支持

[nginx.vim - initial version : vim online](https://www.vim.org/scripts/script.php?script_id=1886)

![image.png](vim%E5%BC%80%E5%90%AFnginx%E9%85%8D%E7%BD%AE%E8%AF%AD%E6%B3%95%E9%AB%98%E4%BA%AE%20116526468f4b81e881f0f2adcf84b2d3/image.png)

> 下载指定的文件，然后放到指定的nginx的机器上
> 

### 移动文件到指定目录

> 移动 `nginx.vim`  到 `~/.vim/syntax` 下，如果没有需要创建
> 

```bash
mkdir ~/.vim/syntax 
mv nginx.vim ~/.vim/syntax 
```

### 修改vim配置

> 在 `~/.vim/filetype.vim` 下添加，没有该文件，需要创建。中间的是需要生效的目录配置
> 

```bash
au BufRead,BufNewFile /etc/nginx/*,/usr/local/nginx/conf/* if &ft == '' | setfiletype nginx | endif

```