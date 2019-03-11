## hexo

- 用Material design设计, 搭建的 [hexo-theme-matery](https://github.com/blinkfox/hexo-theme-matery)
- 在用 `gittalk`的时候需要先在 [github](https://github.com/settings/applications/996580) 注册应用, 填写需要注意的是 `Homepage URL`和`Authorization callback URL`是一个你的博客地址,然后用到`Client ID`和`Client Secret` 去`_config.yml`配置.

## win快速启动工具

- [Wox](http://www.wox.one/)
- [launchy](http://www.launchy.net/)
- [runz](https://github.com/goreliu/runz)
- [utools](https://u.tools/)

## 在windows上使用wget和curl

### 安装[scoop](https://scoop.sh/)

1. 打开 PowerShell 3，运行Set-ExecutionPolicy RemoteSigned -scope CurrentUser 回答 yes
2. 继续在 PowerShell 3 运行 iex (new-object net.webclient).downloadstring('https://get.scoop.sh')

> 如果出错,需要运行 `powershell` 改变执行策略

### 安装wget和curl和sudo

`scoop install wget`, 其他两个一样