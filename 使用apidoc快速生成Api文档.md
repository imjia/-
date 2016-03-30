###安装nodejs
#####1.首先安装homebrew（http://brew.sh/  ）
```
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
```
#####2.利用brew安装node
```
brew install node
```
#####3.安装npm
安装npm有俩方法，任选其一，如下
```
curl http://npmjs.org/install.sh | sh 
```
```
wget http://npmjs.org/install.sh | sh 

// wget 执行完之后
sh install.sh
```
#####4.利用npm安装apidoc
```
sudo npm install apidoc -g
```
#####5.从github下载apidoc
```
git clone https://github.com/apidoc/apidoc.git
```
#####6.利用apidoc生成doc文档
* 任选桌面一个位置，创建一个文件夹例如（`myapp`）。
* 保证github下载下来的`apidoc` 和`myapp`文件夹在同一级目录里，比如都放在桌面。
* 创建`.h`、`.php`、`.java`任选其一后缀名文件。

从`apidoc`及`myapp`的上级目录执行简单的脚本，就可生成api文档了
```
apidoc -i myapp/ -o out/ -t template -f ".h"
// -i 指定输入文件夹
// -o 指定输出文件夹
// -t 指定模板(用来生成静态接口文档页面)
// -f 需要解析的后缀名
// 这个命令表示解析myapp下的所有.h文件，然后生成文档到out目录下，使用的生成模板是mytemplate(不指定，会有默认的模板)，这里的.h可以替换为你的文件后缀
```
如果你看到如下输出，就说明我们成功了。
```
info: Done.
```
否则... 根据错误提示去修改吧。

那么假设你成功了，接下来就可以去查看我们的api文档了，进入`out文件夹`打开`index.html`，你讲看到如下的网页，大功告成，开心的写我们的文档吧！
![Alt text](./QQ20160330-0.png)

-----------
相关连接
[Node.js&NPM的安装与配置](http://www.infoq.com/cn/articles/nodejs-npm-install-config/)
[使用apidoc生成RESTful风格API文档](http://desluo.com/2016/01/26/apidoc/)
[apidocjs官方网站](http://apidocjs.com)

