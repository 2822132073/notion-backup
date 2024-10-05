# vim

vim配置文件位置： `/etc/vim/vimrc`

### 配置tab转换为空格

> 默认的tab是8个空格，先设置为4个空格
`expandtab`表示将tab转换为空格
`shiftwidth`为缩进的宽度
> 

```bash
set tabstop=4 
set expandtab
set shiftwidth=4
```