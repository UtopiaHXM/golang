## Golang 下载

国内地址:
<http://golangtc.com/download>
官网英文地址(自备梯子):
<https://golang.org/dl/>


## Golang 官网

<http://golang.org/>


## 设置系统环境变量
```
$ subl .bashrc

# Golang environment variable
export GOROOT=$HOME/go
export PATH=$PATH:$GOROOT/bin
export GOPATH=$HOME/code/golang

$ source .bashrc
```


## 编译go源码
```
$ cd $GOROOT/src
$ ./all.bash
```
编译过程大概10分钟


## sublime 安装 Package Control

按下快捷键 Ctrl + `
输入以下内容,回车:
```
import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print 'Please restart Sublime Text to finish installation'
```
Preferences菜单下，多出一个菜单项 Package Control


## 安装GoSublime插件

Preferences >> Package Control

输入并选择 Install Package

再新输入框输入并选择 GoSublime


## GoSublime环境变量设置

Preferances >> Package Settings >> GoSublime >> Settings-Default
```
"env": {
    "GOPATH": "$HOME/code/golang",
    "GOROOT": "$HOME/go"
}
```
设置GoSublime缩进
```
// whether or not to indent with tabs (alignment is always done using spaces)
"fmt_tab_indent": true,

// the assumed width of the tab character (or number of spaces to indent with)
"fmt_tab_width": 4,
```

## 设置Sublime缩进

Preferances >> Settings-Default
```
// The number of spaces a tab is considered equal to
"tab_size": 4,

// Set to true to insert spaces when tab is pressed
"translate_tabs_to_spaces": true,
```

## 设置等宽字体

不设置的话,缩进看起来会很奇怪

Preferances >> Settings-User
```
"font_face": "Courier New",
"font_size": 11.0,
```


## git配置别名
```
$ git config --global alias.st status
$ git config --global alias.co checkout
$ git config --global alias.ci commit
$ git config --global alias.br branch
```
甚至还有人丧心病狂地把lg配置成了:
```
$ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
配置Git的时候，加上--global是针对当前用户起作用的，如果不加，那只针对当前的仓库起作用。

每个仓库的Git配置文件都放在.git/config文件中
而当前用户的Git配置文件放在用户主目录下的一个隐藏文件.gitconfig中
别名就在[alias]后面，要删除别名，直接把对应的行删掉即可
