---
layout: post
title: Git汇总
date: 2022-08-12 14:17
categories:
  - 工具
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

# Github
* [如何高效的使用github](http://www.ixirong.com/2015/06/07/git-and-github-repo/)
* [搬进 Github](http://gitbeijing.com/)文字版
* [手机上的github编辑工具:prose](https://github.com/prose/prose)
* [如何高效利用GitHub](http://www.yangzhiping.com/tech/github.html)
* [我在GitHub的工作是怎样的](http://blog.jobbole.com/21270/)
* [GitHub第一年的10个启示](http://blog.jobbole.com/13403/)
* [GitHub如何运作：时间并不决定一切](http://blog.jobbole.com/6492/)
* [GitHub如何运作：异步工作](http://blog.jobbole.com/6815/)
* [GitHub如何运作：创新很重要](http://blog.jobbole.com/7547/)
* [GotGitHub](http://www.worldhello.net/gotgithub/index.html)
* [Github秘籍](https://snowdream86.gitbooks.io/github-cheat-sheet/content/zh/index.html)
* [Github学习指南](https://github.com/jasonim/github-guide)
* [github action官方文档](https://docs.github.com/cn/actions)
* [github action从入门到精通相关资源](https://zhuanlan.zhihu.com/p/387888331)

# Gitbook
* Gitbook FAQ中显示记录数无法汉化？如：`16 ARTICLES`
* [Gitbook语法](https://cowmanchiang.me/gitbook/gitbook/contents/how/code.html)
* [Gitbook文档](https://chrisniael.gitbooks.io/gitbook-documentation/content/)
* [GitBook简明教程](http://www.chengweiyang.cn/gitbook/index.html)
* [Gitbook语法](https://cowmanchiang.me/gitbook/gitbook/contents/how/code.html)
* [Gitbook文档(中文版)](https://www.gitbook.com/book/chrisniael/gitbook-documentation/details)
* [GitBook 简明教程](http://www.chengweiyang.cn/gitbook/index.html)
* [Mac下GitBook制作电子书](http://liaoer.net/2015/04/30/Mac%E4%B8%8BGitBook%E5%88%B6%E4%BD%9C%E7%94%B5%E5%AD%90%E4%B9%A6/)
* [GitBook 插件](http://gitbook.zhangjikai.com/plugins.html)
* [Gitbook，这个开源出书平台了不起](https://linux.cn/article-6792-1.html):柯文哲

# 参考
* [中文技术开源书](https://github.com/larrycai/kaiyuanbook/wiki)
* [Git权威指南](https://gotgit.readthedocs.io/en/latest/): 含目录
* [Pro Git](https://bingohuang.gitbooks.io/progit2/content/): [官网](https://git-scm.com/book/zh/v2)
* [Git自动换行符](https://www.jianshu.com/p/f13ef9e538e0): 文末的实践原则
* [Git Submodule使用完整教程](https://developer.aliyun.com/article/27002)：详细的实践步骤，好点的[排版](https://www.cnblogs.com/lsgxeva/p/8540758.html)
* [Git教程](https://www.liaoxuefeng.com/wiki/896043488029600)
* [猴子都能懂的Git入门](https://backlog.com/git-tutorial/cn/intro/intro1_1.html)
* [Hexo 自动部署到 Github](https://lotabout.me/2016/Hexo-Auto-Deploy-to-Github/)
* [Git学习分支](https://learngitbranching.js.org/?locale=zh_CN)：不错的动画效果，远程部分还没看完
* [Git文档中文版](https://git-scm.com/book/zh/v2)
* 阮一峰
  * [Git 原理入门](http://www.ruanyifeng.com/blog/2018/10/git-internals.html)
  * [常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
  * [Git 使用规范流程](http://www.ruanyifeng.com/blog/2015/08/git-use-process.html)
  * [git cherry-pick 教程](http://www.ruanyifeng.com/blog/2020/04/git-cherry-pick.html)
  * [如何撤销 Git 操作？](http://www.ruanyifeng.com/blog/2019/12/git-undo.html)
  * [git bisect 命令教程](http://www.ruanyifeng.com/blog/2018/12/git-bisect.html)
  * [Git 工作流程](http://www.ruanyifeng.com/blog/2015/12/git-workflow.html)
  * [Git远程操作详解](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)
  * [Git分支管理策略](http://www.ruanyifeng.com/blog/2012/07/git.html)
