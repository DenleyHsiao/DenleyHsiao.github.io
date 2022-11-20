---
layout: post
title: glog使用
date: 2022-11-18 09:44
categories:
  - 技术
---

glog中的使用总结
<!-- More -->

Q: 使用自定义输出格式
A: 只能源码安装：glog编译前执行`cd build && ccmake ..`，打开`WITH_CUSTOM_PREFIX`开关，使用时不用定义GLOG_CUSTOM_PREFIX_SUPPORT宏了
