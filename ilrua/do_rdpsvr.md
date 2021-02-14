# 桥接RDP

> 本章介绍了如何利用MiaoFrp建立RDP服务。

### 云

* 选择隧道类型

选择使用RDP类型。

* 设置映射IP

默认输入127.0.0.1即可。这指向您的主机。

* 设置端口

一般的，Windows默认RDP端口为3389，不排除您已经自定义了端口的情况

* 设置外网端口

外网端口必须大于等于1024，小于等于65535。我们可以点击 `随机端口` 按钮让服务器给你随机分发一个端口，它不会被占用。

* 复制网址

在侧栏找到“隧道列表”，找到您刚才创建的隧道，获取它的网址。

### Windows

* 保存和映射

在侧栏找到 `配置文件` 选项。复制黑底色字，在客户端（frpc.exe）同一目录下创建一个文本文件，粘贴复制的内容，另存为 `frpc.ini` 。在同一目录下运行cmd，输入 `frpc -c frpc.ini`  ，映射就开始了。

* 启动和享用

右击此电脑（这台电脑/计算机），单击“属性”项目，在侧栏找到“远程设置”，单击。在弹出的窗口中勾选“允许远程连接此计算机”选项。

同时按住徽标键和R键，在弹出的窗口中的填空输入 `mstsc` ，敲击Enter键。

在弹出的窗口中的名为“计算机”的填空中输入 `<系统分发的网址>:<远程端口>` ，点击连接按钮。

* 错误处理

如果访问出现提示 `您的凭据不工作` ，确保其它都是对的情况下，可如下设置：

win + R  输入 ` gpedit.msc` 

计算机配置-管理模板-windows组件-远程桌面服务-远程桌面会话主机-安全-远程（rdp）连接要求使用指定的安全层，更改为启用 -rdp ，保存退出。