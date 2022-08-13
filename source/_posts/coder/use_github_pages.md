---
layout: post
title:  "使用Github Pages建站"
date:   2022-03-24 14:51:20
categories:
  - 技术
---

有人说：把自己当成一个公司去经营，如何展示公司的产品呢？
有人说：持续输出倒逼输入

1. 在github上新建`<user_name>.github.io`项目: public权限/.gitignore选择node;
2. aliyun域名解析中增加一条CNAME指向`<user_name>.github.io`;
3. 设置项目`<user_name>.github.io`为，github page使用gh-pages分支，CNAME指向上一步中设置的域名;
3. 构建
```bash
git clone git@github.com:<user_name>/<user_name>.github.io
cd <user_name>.github.io
hexo init <web_name>
cd <web_name>
vi <web_name>/source/_posts/welcome_to_my_web.md
git push origin master
```
4. 部署：提交后的代码会在action下自动更新到gh-pages分支
5. 测试：在浏览器中输入域名

*注*
* 域名解析后需要些时间访问才能生效;
* 提交到github后也需要些时间才能生效：自动执行action需要时间;
* 作为page的github项目必须是public.
