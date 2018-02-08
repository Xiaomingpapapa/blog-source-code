---
title: Hexo + Github + 腾讯云 == 个人博客
categories:
- 学习
---
作为一名程序员，我相信大家很多时间都处于不断学习进步的过程  
那么学习中，难免有不少感悟及收获，想试着记录下来，方便日后与志同道合的小伙伴分享交流  
很多人想到了博客，虽然现在国内的博客平台已经有不少，但就我自身的感受而言，
大多博客都不够简约美观，我只是想简单记录学习心得罢了，你给我整那么多七七八八的功能干啥  
这个时候，我发现了 Hexo 这个强大的平台，十分适合像我这种想要个性化定制博客的程序猿

## Hexo
### 前置条件
> * node.js
> * git
### 安装 Hexo
在 windows 环境下安装Hexo,步骤简单，打开cmd
1. 由于 Hexo 基于 node.js，因此当安装完 node.js 环境之后，我们只需要使用下面命令安装 Hexo
```
$ npm install -g hexo-cli
```
2. 验证 Hexo 安装是否成功，在控制台输入 hexo v 命令，看是否出现版本信息
![hexo version](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/hexoversion.PNG?raw=true)
3. 创建博客工作目录，在该目录中使用cmd 执行下面命令，进行 Hexo 的初始化
```
$ hexo init
```
4. 初始化完成后的博客文件目录如下
![blog workspace](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/blogworkspace.PNG?raw=true)
5. 此时，Hexo 的工作环境算是创建完成，可以通过以下命令进行本地调试
```
$ hexo s(server)
```
6. 在本地部署成功之后，可以直接通过浏览器打开 'http://localhost:4000/'，会出现下图初始页面
![hexo initial page](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/bloginitialpage.PNG?raw=true)

## Hexo && Github
### Github仓库创建
关于 Github 相信各位猿们一定不陌生，假如有没接触过的或者了解不是很深的，可以参考一下这个小姐姐
生动形象的描述[Github是什么？](https://www.zhihu.com/question/20070065)
了解完 Github 之后，接下来我们需要建立本地 Hexo 工作目录与远程 Github 仓库之间的联系
1. 注册一个 Github账号
![signupgithub](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/signupgithub.PNG?raw=true)
2. 创建一个 Github 远程仓库，来存储 Hexo 发布的静态资源，以便可以直接通过访问 Github Page 的方式访问我们的博客   
这边需要注意的是，这个仓库名必须是 username.github.io 格式。  
例如我的用户名是 xiaomingpapapa，那么我的博客仓库名得是 xiaomingpapapa.github.io。  
因为我已经创建了一个同名的仓库，所以下图报错。
![creategighubrepository](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/crategithubrepository.PNG?raw=true)
### 建立本地与Github的连接
3. 远程的 Github 博客仓库也准备好了，接下来我们需要建立 本地Hexo博客与远程Github仓库之间的联系了
这个时候我们之前安装的 Git客户端派上了用场。  
首先需要配 SSH 密钥，这个是本地Git与Github通信的暗号，配钥匙的过程大家可以自己了解一下，在这里就不详细说明了
### 远程部署
4. ssh密钥设置好了之后，这个时候相当于万事具备，只欠东风了。  
我们再回到之前创建的 hexo 目录，打开 _config.yml配置文件，配置 Hexo的远程部署方式，如下：
![deploymentconfig](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/deploymentconfig.PNG?raw=true)
5. 我们在 Hexo工作目录中打开 cmd, 输入以下命令，首先生成本地静态网页资源，存放在 public 文件夹中
```
$ hexo g(generate)
```
6. 本地的静态网页也已经准备好了，我们进入最后阶段，输入以下命令将静态网页推送到 远程的Github
```
$ hexo d(deploy)
```
7. 验收阶段，在浏览器输入你之前在 Github上 创建的博客仓库名称，出现博客页面就证明本次搭建任务初步已经完成
![githubpage](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/githubpage.PNG?raw=true)

## Hexo && Github && 腾讯云域名
### 腾讯云域名
既然是个人博客，怎么能没有属于自己的域名呢，我用的是腾讯云域名解析，当然也有很多相当不错的域名服务
1. 在腾讯云注册账号之后，选择域名注册
![buydomainname](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/buydomainname.PNG?raw=true)
2. 不同的域名类型价格不太一样，大家按照自己的需求意向进行注册购买
![registerdomainname](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/registerdomainname.PNG?raw=true)
3. 购买完成之后，进行域名设置，需要注意的是，刚买的域名还不能够正常解析，需要通过腾讯云的实名认证  
以下是我通过实名认证之后的正常页面
![setupdomainname1](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/setupdomainname1.PNG?raw=true)
4. 点击解析，进行域名的解析设置，需要提一下的是记录值填写的是 github blog page 所对应的主机IP地址
![setupdomainname2](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/setupdomainname2.PNG?raw=true)
5. 如果不知道 github blog page 所对应的IP地址，可以通过cmd ping 自己的博客仓库名称  
例如 ping xiaomingpapap.github.io
![getgithubpageip](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/getgithubpageip.PNG?raw=true)
6. 域名解析设置完成之后，就到了最后的验收阶段了，在浏览器输入自己的域名之后，出现熟悉的博客界面
![testdomainname](https://github.com/Xiaomingpapapa/Blog-Picture/blob/master/Post%20Picture/Hexo%20Blog/testdomianname.PNG?raw=true)








 


