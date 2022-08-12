---
layout: post
title: 编程经验汇总
date: 2022-08-12 09:00
categories:
  - 技术
---

个人多年编程经验汇总
<!-- More -->

* 不要把自己绑定在一门已经过时的技术上，如corba
* 不要All in压注于一个新鲜领域，如小程序
* yml配置文件中":”后面只能是一个空格而不是一个tab
* 所有的编辑器初始都应设置tab为2个空格
* 建议使用大家都认可的缺省值，而不是对个人或组织有特殊意义的: 如2000-01-01就好于2015-11-13作为日期的缺省值。
* 使用源码安装时，建议使用稳定分支，不要使用最新的开发分支master
* 如需Pull Request，建议新开分支再操作
* linux
    * 不要将数据保存在/tmp/目录下，关机就会丢失
    * 建议使用.tar.gz格式的压缩包: `压缩命令是tar -zcvf xx.tar.gz .，对应解压命令是tar -zxvf xx.tar.gz，参数一定要对应，否则会解压失败`
* window
    * ini文件中的key名称不区分大小写
* 使用jupyter写教案
    * 建议使用在线工具：github/gitblit/gist/gitbook/jupyter, 像李宏毅在《机器学习》lesson 4中使用的在线jupyter教案
* Makefile
    * 执行语句前不要有空格，最好以TAB代替空格
    * 变量使用方式是$(CC)，而不是$CC,%CC%等形式
* cmake
    * 建议使用CMake方式编译c++应用程序
    * cmake使用option自定义配置时，缺省值不起作用：比如缺省为"ON"的表现其实是“OFF”, 因为在make之前没有执行ccmake ${project_dir}, 按c和上下键修改，按g键保存退出
* 在有CMakeLists.txt文件的项目中，不要使用clone时已有的Makefile文件，而要通过cmake重新生成
* CI
    * 建议迭代使用持续集成
* docker
    * 建议使用docker而不是虚拟机生成一个开发环境/运行环境
    * 建议通过官网提供的docker安装/docker-compose安装方法，不要使用apt-get之类的安装方法：版本旧，还不容易安装成功
    * 建议docker run时增加-v和-p参数: 以后在使用docker attach container_id时可以共享文件与端口，如：docker run -it -v $(pwd):/home/denley/work -p 3000:3000 denley/dev:full
    * 建议dockerfile中所有的文件复制均使用 COPY 指令，仅在需要自动解压缩的场合使用 ADD, 如果 <源路径> 为一个 tar 压缩文件的话，压缩格式为 gzip, bzip2 以及 xz 的情况下，ADD 指令将会自动解压缩这个压缩文件到 <目标路径> 去
    * 建议使用docker build而不是docker commit新建一个镜像
    * Dockerfile中的指令必须是大写字母
    * Dockerfile指令不要过早优化，以便充分利用缓存加速build，验证成功后可交由automated。
    * 多使用docker-compose
* db
    * 建议db中使用缺省值代替null值以解决Nulls first/last排序问题, 对有null值的字段进行排序时，不同的数据库有不同的处理方式，查询结果在排序方面极不可控
* 环境变量
    * 建议环境变量全部大写
    * 建议纳入版本控制系统的涉密信息采用环境变量的方式设置, 如：Rails中的<%= ENV.fetch("SITE_DATABASE_PASSWORD") { "123456"} %>，可能其它语言不一定支持
* git
    * 使用github保存code
    * 使用gist保存code片段
    * 使用gitbook写书
        * gitbook中SUMMARY.md不能使用带'-'的文件名，如chiron-2.md应改为chiron_2.md
        * gitbook设置域名解析时CNAME指向：www.gitbooks.io/hosting.gitbook.com，并要点启用后等10分钟才会生效，如还有问题，清空浏览器缓存
    * 不要使用git保存不是很了解内部结构的文件夹，如数据库、git仓库之类 因为其客户端可能对空目录敏感：即使有.gitignore/.gitkeep之类的隐藏文件，如postgres数据库有些空目录不存在时就无法启动，而git对空目录是不纳入版本控制的，可通过压缩整个文件夹后再纳入版本控制
* web
    * 路由时图片后缀区别大小写，整个路由路径呢？如：http://domain.name/images/PCLint-Directory.JPG与http://domain.name/images/PCLint-Directory.jpg不是同一文件
