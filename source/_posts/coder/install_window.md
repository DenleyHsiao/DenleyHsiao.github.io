---
layout: post
title:  windows系统安装
date:   2022-04-29 16:49:08
categories:
  - 系统
---

针对本人MAC下的虚拟机win7_64旗舰版
<!-- More -->

* OS下载：[个人](https://msdn.itellyou.cn/)或者[微软下载中心](https://www.microsoft.com/zh-cn/software-download)
* 使用[老毛桃](https://www.laomaotao.net/)制作windows启动盘
* [驱动精灵万能网卡版](http://www.drivergenius.com/)
* 运行win7激活工具
* 安装[VIM](https://www.vim.org/download.php#pc)，并配置好;
* 安装mtux，并配置好；
* 安装[git](https://git-scm.com/download/win)/[git GUI](https://tortoisegit.org/download/)及汉化包，并配置好git;
* 为便于`git clone git@github.com:xxx/yyy`时无需密码验证, 进行[github下的ssh](https://www.jianshu.com/p/9317a927e844)配置

# V1
用于STC下的开发工作，建议安装最新v5版本
* 执行MDKxxx.exe安装IDE,缺省安装了ARM;
* 手动安装c51，期间出现的所有提示都选skip;
* 运行注册机
```shell
1. 右键以管理员身份打开IDE的桌面快捷方式;
2. 打开“File”的“License Management”，拷贝其CID编号;
3. 打开注册机keygen，粘贴CID编号;
4. target”选择arm，点击“Generate”，复制结果到“License Management”中，点“Add Lic”，激活ARM
5. 同样操作激活C51.
```

* 安装烧录工具(stc-isp-15xx-v6.86S)

# V2
SD卡备份与恢复：Win32DiskImager
* 恢复: 选择指定image文件后Write
* 备份: 选择指定image文件后Read，但只能手动输入保存文件路径，如：C:\RaspberryPi.img

# 附录
* windows下的包管理工具：[scoop](https://sspai.com/post/52496)、[baulk](https://github.com/baulk/baulk)
* everything
* autohotkey
* Total Commander
* win10截图：snippingtool
* SD卡格式化：SDFormatter

# 注意
* 微软下载中心的”Oct 2018"版本有问题，应选”April 2018“
