![](https://github.com/denleyhsiao/denleyhsiao.github.io/workflows/build_and_deploy/badge.svg?branch=master)

# Blog
* [个人博客](https://blog.justtodo.com)

# 使用
1. 执行`./misc/git_update.sh`, 因为它依赖于[blog项目](https://github.com/denley-say/blog)
2. 修改提交后会通过github action自动部署到gh-pages分支

# 注意
* 自动部署中使用了`secret.FROM_BLOG_ACCESS_TOKEN`:在项目的Settings/Secrets中新增，
其值通过个人账户下的Settings/Developer Settings/Personal access tokens生成（此值只在第一次生成时显示）
