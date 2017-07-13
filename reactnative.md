## Homebrew
是Mac上的软件管理工具。
```
//软件安装
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
//搜索
brew search mysql
//查询:主要看具体的信息，比如目前的版本，依赖，安装后注意事项等
brew info mysql
//更新:这会更新 Homebrew 自己
brew update
//检查过时（是否有新版本）：列出所有安装的软件里可以升级的那些
brew outdated
//升级:升级所有可以升级的软件们
brew upgrade
//清理：清理不需要的版本极其安装包缓存
brew cleanup 
```
## IDE
采用[Atom＋Nuclide](http://blog.csdn.net/hello_hwc/article/details/51612139)的方式IDE
## flow
进行静态语法检查，自动补全
## 项目的React-Native版本升级
在项目目录下命令`react-native-git-upgrade`
