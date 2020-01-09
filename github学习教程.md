
# github学习教程

[toc]
## 1、什么是 Github?
<img src="https://upload-images.jianshu.io/upload_images/4064394-275d48bd7cb63cf5.png?imageMogr2/auto-orient/strip|imageView2/2/w/600/format/webp"/>

GitHub就是全是界程序员和组织发布程序代码的平台之一，全世界各地的程序员讲自己写的代码上传到这里与大家分享。
>当我们自己去开发某个功能（**利用leaflet加载热力图**），可以尝试先去GitHub借鉴一下别人已经开发过的。

或者你和同伴们打算开发一个小软件，就可以将代码放到GitHub上来实现合作开发。
**使用GitHub,首先要会使用Git**。


## 2、Git极简入门
### 2.1、Git是什么？
> 版本控制器，类似于我们目前用的svn，但是和svn也有一定的区别。主要区别在于集中式和分布式。
<h4><a href="https://blog.csdn.net/qq_40143330/article/details/79816024">svn与git的区别</a></h4>

- 集中式版本控制系统：版本库是集中存放在中央服务器的，而干活的时候，用的都是自己的电脑，所以要先从中央服务器取得最新的版本，然后开始干活，干完活了，再把自己的活推送给中央服务器。​集中式版本控制系统最大的毛病就是必须联网才能工作。
<img src="https://images2018.cnblogs.com/blog/872610/201806/872610-20180608145946789-1176396152.png"/>

- 分布式版本控制系统：分布式版本控制系统根本没有“中央服务器”，每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。比方说你在自己电脑上改了文件A，你的同事也在他的电脑上改了文件A，这时，你们俩之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。
<img src="https://images2018.cnblogs.com/blog/872610/201806/872610-20180608150004492-762162766.png"/>

### 2.2、使用Git
1、去Git官网下载对应操作系统的Git
2、设置Git
```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```
3、使用Git，使用**git init**命令后，这个文件夹以后的更改就会被记录了
**把一个文件放到Git仓库只需要两步**
1)、我们使用git add命令，告诉git我们把文件添加到仓库缓存区了

```
git add index.html
```
2)、使用git commit命令，告诉git我们要把缓存区的所有文件正式提交到仓库
```
git commit -m "jwl添加了index.html"
```
-m 后面的话就相当于 我们每次提交代码的注释，告诉别人自己提交了啥
3)、输入**git log**命令查看版本情况
4)、实现版本回退
```
git reset --hard HEAD^ //回退上一个版本
git reset --hard 88d885 //回退到固定版本
```
（演示时，可提交多个文件，来回修改，以及修改内容，并回退）

## 3、GitHub使用
### 3.1、<a href="https://github.com/join">邮箱注册</a>
### 3.2、配置
> 创建SSH Key，你的电脑就和你的GitHub账号联系

1、 此处邮箱就是创建时候的邮箱
```
ssh-keygen -t rsa -C "youremail@example.com"
```
2、 可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
3、 登陆GitHub，打开“Account settings”，“SSH Keys and GPG keys”页面：
然后，点“New SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容即可。
### 3.3、创建仓库，并使用
1、 <a href="https://github.com/new">Create a new repo</a>
2、利用我们之前的git文件夹，进行上传
首先，把本地仓库和远程仓库关联
```
git remote add origin git@github.com:用户名/仓库名.git
```
然后推送
```
git push -u origin master
```
由于远程库是空的，我们第一次推送master分支时，加上了-u参数。以后的话就可以
```
git add 文件/文件夹路径
git commit –m “你的注释”
git push origin master
```
### 3.4、加入其他人的项目，协同作业
1、拥有者，发起邀请（settings-->Collaborators）
2、受邀请者打开
```
https://github.com/jiawanlong/demo/invitations/
```
3、本地下载代码，然后提交
```
git clone https://github.com/jiawanlong/demo.git
```
## 4、日常开发
### 4.1、常见时开发（热力图为例）
遇到一个问题，可以先尝试模糊词搜索，例如leaflet heatmap，默认是根据star（好评）排序的。还可以切换不用的语言进行过滤，选择<a href="https://github.com/Leaflet/Leaflet.heat">第一个看看</a>
1、默认的就是README.md，可以看下这个库的基本概括，同时我们自己开发的东西下面最好也有一个这样的文档，例如开发中心下有个部署的手册。（md是通用的标记语言，简化html)
2、如果只是利用开发，则直接**Clone or download**，如果想据为己有，怕人家翻脸无情的删除东西，或者做出改变，可以fork一下下，如果你觉得人家不错，给个好评吧！
```
git clone https://github.com/jiawanlong/Leaflet.heat.git
```
3、本地运行示例，进行调试
### 4.2、被迫时开发
查阅<a href="https://leafletjs.com/plugins.html">文档</a>的时候，遇到链接，不要慌，慢慢来，实在不行，右键,翻译成中文。
### 4.3、好奇时开发
闲着没事时，可以在主页多搜索公司相关，或者其他科技公司相关的东西（supermap,google），有很多意向不到的收货。很多公司开发的新的东西，已经提交开源，没来得及宣传，我们要主动学习。