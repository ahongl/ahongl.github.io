# ahongl.github.io
**前期准备**
拥有一个Github账号 ([注册](https://github.com/)),并且已经创建自己的github Pages的项目([教程](https://pages.github.com/))
本地电脑的公钥已经加入到Github上了,[如何生成本机公钥](http://blog.csdn.net/hustpzb/article/details/8230454)
本地电脑上已经[安装Node.js](http://blog.csdn.net/baihuaxiu123/article/details/51868142),安装Git
本地Git的邮箱、用户名已经配置成功
**安装**
Hexo是基于Node.js的,所以必须在电脑上安装Node.js，上面有教程。
Node.js安装好了后,执行以下命令

```
$ npm install hexo-cli -g 
```

 - npm是Node.js安装时自带的类库,是目前全球最大的类库之一,比Maven仓库还大,类似CentOS的yum源,Mac
 - OX中brew的软件库 通过npm install可以直接安装基于Node.js的所有插件

安装完成后,我们一般在工作目录或者用户目录创建一个网站目录,比如blog目录

```
$ mkdir blog 
```
然后通过blog目录创建站点

```
$ hexo init blog
```
出现

```
INFO  Start blogging with Hexo!
```
表示安装成功
安装完成后,进入blog站点目录,安装一下npm插件支持

```
$ cd blog
$ npm install
```
**启动站点**

```
$ hexo server
INFO  Start processing
INFO  Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.
```
**查看站点**

在浏览器中查看http://localhost:4000/
**一键部署到Github**
**配置Github**
在blog目录,打开_config.yml

```
$ vim _config.yml
```
修改配置文件_config.yml中deploy下的内容

```
 68 # Deployment
 69 ## Docs: https://hexo.io/docs/deployment.html
 70 deploy:
 71   type: git
 72   repo: https://github.com/chwshuang/chwshuang.github.com.git
 73 branch: gh-pages
```
**安装部署插件**
配置修改完成后,需要安装部署插件: 
安装 hexo-deployer-git 插件: 在blog目录执行以下命令即可

```
$ npm install hexo-deployer-git --save
```
**编译部署**
插件安装完成后,执行项目清理和静态网页生成

```
$ hexo clean ; hexo genarate
```
安装完成后进行部署

```
$ hexo deploy
```
**查看结果**
然后到你的Github上项目的主页,看看master分支上的代码更新时间，为刚刚更新即为成功
**更新主题**
可以在：https://hexo.io/themes/这个网站上找到喜欢的主题
**下载**
进入blog目录,克隆主题到本地

```
$ git clone https://github.com/tufu9441/XXXX.git themes/XXXX
XXXX为你喜欢的主题的名字，本地的名字可以自己起
```
**安装主题**
**安装**
*注意: 某些主题可能需要安装Node.js的插件,在安装主题时,最好在主题的Githu主页看看安装步骤*
下面是一个例子（maupassant-hexo）：

```
$ vim _config.yml
...

 63 # Extensions
 64 ## Plugins: https://hexo.io/plugins/
 65 ## Themes: https://hexo.io/themes/
 66 theme: maupassant
```
这个主题依赖jade和sass插件,所以在配置好主题后,还要进行安装插件

```
$ npm install hexo-renderer-jade --save
...
$ npm install hexo-renderer-sass --save
```
**查看**
先清空缓存,然后启动服务器,在本地浏览器输入[localhost:4000/](localhost:4000/)查看效果

```
$ hexo clean 

$ hexo s --debug
```
**自定义**
如果要修改主题的内容,可以在主题的Github主页上查看详细介绍
**写文章**
在blog目录下执行创建文章指令

```
$ hexo new "blog1"
INFO  Created: ~/blog/source/_posts/blog1.md
```
然后修改source/_posts/blog1.md文件

```
$ vim source/_posts/blog1.md
  1 ---
  2 title: blog1
  3 date: 2016-08-25 18:50:03
  4 tags:
  5 ---
  6 
  7 我的第一篇文章！
```
清理后启动,就可以看到博客中新增加的文章了。

```
$ hexo clean
$ hexo s --debug
```
至此一个个人博客就搭建好啦~
前往查看：https://ahongl.github.io/
欢迎大家前往测试评论功能：https://ahongl.github.io/2018/03/28/Hexo+Node.js+Github-creating-a-Community/
