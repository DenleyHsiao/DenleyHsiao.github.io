---
layout: post
title: 串口工具
date: 2022-08-12 14:00
categories:
  - 技术
---

串口工具汇总
<!-- More -->

* 要打开的串口在打开之前需先加上权限，如： `sudo chmod 777 /dev/ttyS1`
*
* 串口通信：
* Window下的：serial_port_utility/SerialDebug和[sscom 串口助手](https://tech.wmzhe.com/article/10085.html)sscom支持串口/网口通信，注意串口通信时可选设置RTS/DTR
* MAC下的：[coolterm](https://blog.csdn.net/bht890811/article/details/74151180): 串口调试助手/[minicom](https://blog.csdn.net/u010285246/article/details/72354038): 串口调试工具

# cutecom
* [ubuntu 安装cutecom串口调试工具](https://blog.csdn.net/shui1025701856/article/details/79277484)
```bash
# 安装
sudo apt-get install cutecom

# 运行
sudo cutecom
```

# xgcom
* [树莓派上使用串口调试工具xgcom](https://shumeipai.nxez.com/2017/04/29/raspberry-pi-using-the-serial-debugging-tool-xgcom.html)
```bash
# 安装编译环境
sudo apt-get install autoconf automake libvte-dev libglib2.0-dev pkg-config libgtk2.0-dev -y

# 编译安装
./autogen.sh && make && sudo make install

# 运行
sudo xgcom
```

# 串口命令
```bash
# 查看串口是否可用，可以对串口发送数据比如对com1口
echo lyjie126 > /dev/ttyS0
# 查看串口名称使用, 一般串口的名称全部在dev下面，如果你没有外插串口卡的话默认是dev下的ttyS* ,一般ttyS0对应com1，ttyS1对应com2，当然也不一定
ls -l /dev/ttyS*
# 查看串口驱动
cat /proc/tty/drivers/serial
# 查看串口设备
dmesg | grep ttyS*
```
