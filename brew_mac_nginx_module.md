# document
为了学习章亦春的nginx学习资料:[agentzh-nginx-tutorials](http://openresty.org/download/agentzh-nginx-tutorials-zhcn.html#00-Foreword01)。因此特意搭建了本地的nginx学习环境。 搭建过程还是遇到了一些坑的。所以还是纪录一下，希望能帮助到其他的学习者。
### nginx安装
最常用的安装方法:
```
brew install nginx
```
但是春哥学习内容里面依赖了很多第三方的nginx模块，而通过此种方法安装, 没有简便的方法把第三方模块加载进来。Google发现一个比较靠谱的办法,但是我按着步骤来，最后还是失败了。在这里我贴一下链接供大家参考:[解决方案](http://googya.github.io/blog/2012/12/22/add-echo-nginx-module-with-brew-in-mac/)

于是我放弃了这种方法安装,google找到了一个开源项目:[homebrew-nginx](https://github.com/Homebrew/homebrew-nginx)
然后按着说明一步一步的安装:
```
brew tap homebrew/nginx
brew options nginx-full 
brew info nginx-full
brew install nginx-full --with-upload-module --with-echo-module 
nginx -V
看到如下包含结果就证明安装成功
... --add-module=/usr/local/share/echo-nginx-module --add-module=/usr/local/share/upload-nginx-module
```
当然以上几个安装步骤还是会出现问题，但是跟着提示或者google能很快的解决

### nginx conf编辑器
本人一直习惯用intellj做代码的编辑，于是也打算用intellj来作为编辑nginx.conf的工具。于是本人找到了一个比较好用的intellj  nginx插件。[插件地址点这里](https://plugins.jetbrains.com/idea/plugin/4415-nginx-support)

### 最后放一张我的工作界面，intellj就是好用，继续学习去了。
![![输入图片说明](https://static.oschina.net/uploads/img/201701/20165741_2uZ2.jpg "在这里输入图片标题")](https://static.oschina.net/uploads/img/201701/20165725_WlyD.jpg "在这里输入图片标题")
