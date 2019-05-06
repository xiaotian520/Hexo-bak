---
title: 使用Github Pages和Hexo搭建自己的独立博客【超级详细的小白教程】
date: 2019-05-06 13:43:57
tags: 
- Hexo
- GitHub Pages
- Blog
categories: 
- 技术教程

---

这是一篇有关如何使用 GitHub Pages 和 Hexo 搭建属于自己独立博客的详尽教程。



<!-- more -->


### 前言

---

我的博客地址：[Xiao Tian's Blog](https://xiaotian520.github.io/)

本人是软件工程专业在校生，目前只学习了Jva和Python编程语言，对网站开发的有关知识几乎为零，这也是我搭建好自己的博客之后写的第一篇博客，刚开始搭建博客的时候自己也是网上各种百度，由于自己属于小白那种，历经了千辛万苦才弄好，所以借这个机会写一篇小白真正能看懂的博客搭建教程，教你一步一步走向成功的彼岸！


### 入门

---

> <center>GitHub Pages</center>

GitHub Pages可以被认为是用户编写的、托管在GitHub 上的静态网页。使用GitHub Pages可以为你提供一个免费的服务器，免去了自己搭建服务器和写数据库的麻烦。此外还可以绑定自己的域名。
> <center>Hexo</center>

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

---

### 安装 Node.js

---

[点击此处](https://nodejs.org/en/download/)访问官网，按需下载相应版本，默认安装可以了

![](../../../../images/nodejs.png)

注：本人在安装过程中出现了Warning 1909,无法创建快捷方式，这种情况很少出现，如果在安装过程中也有这种情况请参考百度文库（win10系统实测可行）：[《Win7安装程序警告1909无法创建快捷方式》](https://wenku.baidu.com/view/4ad59110964bcf84b9d57ba5.html)

![](../../../../images/nodejserror.png)

---

### 安装 Git

---

[点击此处](https://git-scm.com/download/win)访问官网，按需下载相应版本，默认安装即可 
参考资料：[《如何在windows下安装GIT》](https://www.cnblogs.com/jytx/p/5602927.html) 　（By 俊雨廷休）
　　　　　[《Pro Git（中文版）》](http://git.oschina.net/progit/)

#### 检验Git是否安装成功

同时按下 Win 键和 R 键打开运行窗口,输入 cmd ，然后输入以下命令，有相应版本信息显示则安装成功，若不正确可以卸载软件重新安装，此外若安装成功，在桌面右键鼠标，可以看到菜单里多了 Git GUI Here 和 Git Bash Here两个选项，第一个是图形界面的Git操作，另一个是命令行

```
$ git --version  
$ node -v  
$ npm -v
```

看到此信息说明安装成功

![Git Version](../../../../images/gitinstall.png)

![Git 控制面板](../../../../images/git面板.png)

---

### 安装Hexo

---

选择一个磁盘，新建一个文件夹，自己重命名文件夹（如：我的文件夹为：D:\Program Files\Hexo），博客相关文件将储存在此文件夹下，在该文件夹下右键鼠标，点击 Git Bash Here，输入以下 npm 命令即可安装，第一个命令表示安装 hexo，第二个命令表示安装 hexo 部署到 GitHub pages 的 deployer，如图所示即为安装成功

```
 $ npm install hexo-cli -g  
 $ npm install hexo-deployer-git --save  
```

![Hexo安装](../../../../images/HexoInstall.png)

---

### Hexo 初始化配置

---

在刚才新建的文件夹里面再次新建一个 Topxt 文件夹（如：我的文件夹为：D:\Program Files\Hexo\Topxt）,进入该 Topxt文件夹右键鼠标，点击 Git Bash Here，输入以下命令，如图所示则安装成功

```
$ hexo init
```

![hexo初始化](../../../../images/Hexo初始化.png)

Hexo 安装完成后，将会在指定文件夹中自动生成所需要的文件，Hexo 文件夹下的目录如下：

![初始化成功](../../../../images/Hexoinit.png)

---

### 本地查看效果

---

执行以下命令，执行完即可登录 <http://localhost:4000/> 查看效果

```
$ hexo generate  
$ hexo server 
```

显示以下信息说明操作成功：

```
INFO  Start processing
INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
```

访问 <http://localhost:4000/> 查看效果：

![Hexo页面](../../../../images/HexoPages.png)

---

### 部署到 GitHub Pages 上

到目前为止，我们的本地博客就成功搭建了，但是现在我们只能通过本地连接查看博客，我们要做的是让其他人也能够访问我们的博客，这就需要我们将博客部署到Github Pages上

#### 注册 Github 账户

[点击此处](https://github.com/)访问 Github 官网，点击 Sign Up for free注册账户

![注册GitHub](../../../../images/registerGitHub.png)

#### 创建项目代码库

点击  Start  a  project 开始创建，步骤及注意事项见下图：

![](../../../../images/创建仓库.png)

#### 配置 SSH 密钥

只有配置好 SSH 密钥后，我们才可以通过 git 操作实现本地代码库与 Github 代码库同步，在你第一次新建的文件夹里面（如：我的文件夹为：D\Hexo） Git Bash Here 输入以下命令：

```
$ ssh-keygen -t rsa -C "your email@example.com" 
//引号里面填写你的邮箱地址，比如我的是446691726@qq.com
```

之后会出现：

```
Generating public/private rsa key pair.  
Enter file in which to save the key (/c/Users/you/.ssh/id_rsa):  
//到这里可以直接回车将密钥按默认文件进行存储
```

然后会出现：

```
Enter passphrase (empty for no passphrase):  
//这里是要你输入密码，其实不需要输什么密码，直接回车就行 
Enter same passphrase again:
```

接下来屏幕会显示：

```
Your identification has been saved in /c/Users/you/.ssh/id_rsa.  
Your public key has been saved in /c/Users/you/.ssh/id_rsa.pub.  
The key fingerprint is:  
这里是各种字母数字组成的字符串，结尾是你的邮箱  
The key's randomart image is:  
这里也是各种字母数字符号组成的字符串
```

运行以下命令，就会自动将公钥的内容复制到系统粘贴板上

```
 $ clip < ~/.ssh/id_rsa.pub
```

#### 在 GitHub中添加公钥

##### 登陆 GitHub，进入 Settings：

![](../../../../images/githubSetting.png)

##### 点击 SSH and GPG Keys：

![](../../../../images/SSH.png)

##### 选择 New SSH key：

![](../../../../images/newKey.png)

##### 粘贴密钥：

![](../../../../images/addKey.png)

#### 测试

输入以下命令：注意：git@github.com不要做任何更改！

```
 $ ssh -T git@github.com
```

之后会显示：

![](../../../../images/连接github.png)

此时表示设置正确

#### 配置 Git 个人信息

Git 会根据用户的名字和邮箱来记录提交，GitHub 也是用这些信息来做权限的处理，输入以下命令进行个人信息的设置，把名称和邮箱替换成你自己的，名字可以不是 GitHub 的昵称，但为了方便记忆，建议与 GitHub 一致

```
$ git config --global user.name "此处填你的用户名"  
$ git config --global user.email  "此处填你的邮箱"
```

到此为止 SSH Key 配置成功，本机已成功连接到 Github

---

### 将本地文件更新到 Github

---

####  登录 Github 打开自己的项目 your [name.github.io](http://name.github.io/)

![](../../../../images/repositories.png)

#### 鼠标移到 Clone or download 按钮，选择 Use SSH

![](../../../../images/Use SSH.png)

#### 一键复制地址

![](../../../../images/copysite.png)


#### 打开你创建的 Hexo 文件夹（如：D:\Program Files\Hexo\Topxt），右键用记事本（Notepad++或者VS code等都可以）打开该文件夹下的 _config.yml 文件

![](../../../../images/编辑配置文件.png)

#### 按下图修改 _config.yml 文件并保存

```
deploy:
  type: git
  repository: git@github.com:topxt/topxt.github.io.git
  branch: master
```

![](../../../../images/deploy配置.png)

#### 在 Hexo 文件夹下分别执行以下命令

```
 $ hexo g  
 $ hexo d
```

执行完之后会让你输入你的 Github 的账号和密码，如果此时报以下错误，说明你的 deployer 没有安装成功

```
 ERROR Deployer not found: git
```

需要执行以下命令再安装一次：

```
 npm install hexo-deployer-git --save
```

再执行 `hexo g -d`，你的博客就会部署到 Github 上了

#### 访问博客

你的博客地址：[https://你的用户名.github.io](https://xn--6qqv7i14ofosyrb.github.io/)，比如我的是：[https://topxt.github.io](https://topxt.github.io/) ,现在每个人都可以通过此链接访问你的博客了

---


### 在博客上发表文章


---

有关如何在博客上发表文章，可以参考我的另外一篇文章：

---


### 为博客更换主题


---

有关更换Hexo的主题，可以参考我的另外一篇文章：

---


### 设置个性域名


---

有关如何为博客设置个性域名，可以参考我的另外一篇文章：

---


###  结语


---
一顿操作下来虽然有点儿累，但看见拥有了自己的博客还是非常有成就感的，人生就是需要折腾，那么现在就开始你的创作之旅吧！文章的不断积累，你会从中受益很多的！另外，这是一篇小白写的适用于小白的博客搭建教程，比较详细，有这方面基础的可以百度有简略一点儿的教程，文中如有错误还请大佬指出改正！文中涉及参考资料如有侵权请联系我删除！
