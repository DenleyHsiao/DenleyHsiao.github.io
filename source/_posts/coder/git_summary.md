---
layout: post
title: Git汇总
date: 2022-08-12 14:17
categories:
  - 技术
---

git相关问题汇总
<!-- More -->

* Travis-CI: 使用其进行blog的自动化部署
  1. Q: 在使用travis-CI自动部署时邮箱中总是收到如下的build错误：`gh-token is invalid. Details: GET https://api.github.com/user: 401`
  2. A: 最后发现是如下的引号使用的中文: `encrypt 'GITHUB_TOKEN=d645e71ff953dfb2dbb5b5d0b17aef80f5bdbfe1' --add`

* 解决两个账号(denleyhsiao/denleysay)交叉提交问题的[方法1](https://gist.github.com/jexchan/2351996)和[方法2](https://tiffanybbrown.com/2017/06/using-multiple-ssh-keys-with-github/index.html)，在hexo deploy自动提交时很有用 `HostName github.com User git IdentityFile ~/.ssh/denley_say`
* 引用Github上的js文件时，如果报Content-Type之类的错误，可通过[RawGit](https://rawgit.com/)转换后使用。
* 最后一条日志输出
```bash
git log --date=format:'%Y-%m-%d %H:%M:%S' --pretty=format:'%cd %h: %B' -n 1 > VERSION
```

# 备忘
```bash
git commit --allow-empty -m "XXX"
git commit --amend
git pull --rebase
git rebase
git cherry-pick XXX
git submodule update --init
git submodule foreach --recursive git submodule update --init
git submodule sync # 修改子模块URL/local path后
git submodule update --recursive --remote
git rm --cached third_party/CppUnit # 删除子模块后(.gitmodules & .git/config)
git update-index --assume-unchanged /path/to/file # 忽略跟踪
git update-index --no-assume-unchanged /path/to/file # 恢复跟踪
```

# 工具
* GitBook[插件](http://gitbook.zhangjikai.com/plugins.html)
* 权限管理工具: Gitosis
* 代码审核服务器: [Gerrit](https://www.worldhello.net/2010/11/10/2059.html)
* GitStats
* 手机上的Github编辑工具：[prose](https://github.com/prose/prose)

# 参考
* [Git权威指南](https://gotgit.readthedocs.io/en/latest/): 含目录
* [Pro Git](https://bingohuang.gitbooks.io/progit2/content/): [官网](https://git-scm.com/book/zh/v2)
* [Git自动换行符](https://www.jianshu.com/p/f13ef9e538e0): 文末的实践原则
* [Git Submodule使用完整教程](https://developer.aliyun.com/article/27002)：详细的实践步骤，好点的[排版](https://www.cnblogs.com/lsgxeva/p/8540758.html)
* [Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)
* [常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
* [Git远程操作详解](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)
* [猴子都能懂的Git入门](https://backlog.com/git-tutorial/cn/intro/intro1_1.html)
* [GotGitHub](http://www.worldhello.net/gotgithub/index.html)
* [Github秘籍](https://snowdream86.gitbooks.io/github-cheat-sheet/content/zh/index.html)
* [Github学习指南](https://github.com/jasonim/github-guide)
* [中文技术开源书](https://github.com/larrycai/kaiyuanbook/wiki)
* [Gitbook语法](https://cowmanchiang.me/gitbook/gitbook/contents/how/code.html)
* [Gitbook文档](https://chrisniael.gitbooks.io/gitbook-documentation/content/)
* [GitBook简明教程](http://www.chengweiyang.cn/gitbook/index.html)
* [Hexo 自动部署到 Github](https://lotabout.me/2016/Hexo-Auto-Deploy-to-Github/)
