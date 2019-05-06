---

title: V2RayN使用教程
date: 2019-05-03 18:57:51
tags: 
- V2ray
- 科学上网
categories:
- 技术教程

---

V2Ray是一个优秀的开源网络代理工具，可以帮助你畅爽体验互联网，目前已经全平台支持Windows、Mac、Android、IOS、Linux（没电脑上Linux啦）等操作系统的使用。相对起Shadowsocks来说属于后起之秀，在混淆能力、兼容性、速度上有着独到的优点。
<!-- more -->

### 备注

---

以下教程均以使用了一键安装 V2Ray 脚本为前提：[V2Ray 一键安装脚本](https://git.io/v2ray.sh)
如果你还没有安装 V2Ray，可以参考这教程：[V2Ray搭建详细图文教程](../从零开始：史上最详尽V2Ray搭建图文教程)

---

### 下载V2RayN

---
>备注：按住Ctrl+单击，即可在新窗口打开链接
 下载链接： https://github.com/2dust/v2rayN/releases/latest
 然后选择v2rayN-Core.zip下载
 下载好了之后，解压，然后打开解压的文件夹
 目录结构大概如下图所示
 ![V2ray目录](../../../../images/V2ray目录.png "V2ray目录")

---

### 获取 V2Ray 客户端配置

---
XShell 登录你的 VPS （如果你没登录）
输入 `v2ray url`

然后复制 vmess 链接 （将链接全选，然后鼠标右键，再选择复制即可）
(下面这个是VMESS 链接，如果你没有，直接跳过，QQ群都写好了哦。甭管，走下一步，谢谢)
![vmess](../../../../images/vmess.png "vmess")

---

### 配置 V2RayN

---

双击 `v2rayN.exe` 启动，然后在任务栏托盘找到 V2RayN 图标并双击它
添加一个 VMess 服务器
![v2ray添加Vmess](../../../../images/v2ray添加Vmess.png "v2ray添加Vmess")

从剪贴板导入 URL！！！ 群里有VMESS 的链接，复制，然后从剪贴板导入URL即可。
<font size="20px">请加入QQ群获取URL：582482030</font>
![导入Vmess链接](../../../../images/导入Vmess链接.png "导入Vmess链接")
然后点击确定即可
![V2ray添加完成](../../../../images/V2ray添加完成.png "V2ray添加完成")
V2RayN 启用系统代理
在任务栏托盘找到 V2RayN 图标并鼠标右键，先启动系统代理，然后更新PAC，之后，系统代理模式>PAC 模式
![启用系统代理](../../../../images/启用系统代理.jpg "启用系统代理")
备注，选择 更新 PAC 之后，双击打开 V2RayN 图标打开主界面在下面信息那里看看有没有显示 PAC更新成功！
![访问谷歌](../../../../images/访问谷歌.png "访问谷歌")

---

### 结束

---

V2RayN教程结束，再见，朋友们。

有任何问题，请大家在下方留言，我会尽快给大家回邮件。