---
layout: post
title: MAC系统安装
date: 2022-08-12 09:24
categories:
  - 系统
---

针对本人MAC系统下的安装
<!-- More -->

# 前提
* [brew安装](https://brew.sh/index_zh-cn)
```bash
  # 安装brew
  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

  # 更换源
  cd "$(brew --repo)"
  git remote set-url origin https://mirrors.ustc.edu.cn/brew.git
  cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
  git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
  brew update
```

# 软件
* 自动安装
```bash
  # Console，其中的docker是客户端
  brew install boost autojump docker docker-compose docker-completion docker-compose-completion wget you-get
  brew install --HEAD https://gist.githubusercontent.com/Kronuz/96ac10fbd8472eb1e7566d740c4034f8/raw/gtest.rb

  # GUI
  brew cask install shadowsocksx-ng yinxiangbiji  alfred google-chrome iterm2 textmate the-unarchiver github teamviewer cmake sogouinput vlc mounty aliwangwang thunder baidunetdisk obs xmind-zen shuttle
  brew cleanup
```

* 下载安装
* [docker服务端](https://docs.docker.com/desktop/install/mac-install/): 设置国内镜像来加速http://f1361db2.m.daocloud.io
* [OpenInTerminal](https://github.com/Ji4n1ng/OpenInTerminal/blob/master/README-zh.md)
* [sogou五笔](https://pinyin.sogou.com/mac/)
* [oh-my-zsh](https://ohmyz.sh/)
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

# 设置
* 系统启动顺序
* 启用FN键
* Textmate设置
  * 下载文件后重启
  ```bash
  cd ~/Library/Application\ Support/TextMate/Managed/Bundles/
  # 高亮显示空格
  git clone https://github.com/mads379/Whitespace.tmbundle.git

  # 自动去掉行尾空格
  git clone https://github.com/bomberstudios/Strip-Whitespace-On-Save.tmbundle.git
  # 自动生成尾行
  git clone https://github.com/hajder/Ensure-New-Line-at-the-EOF.tmbundle.git
  ```
  * 设置textmate的tab: ~/.tm_properties
  ```bash
  softWrap = true
  tabSize = 2
  softTabs = true
  ```
* 其它设置
```bash
brew link docker docker-compose --overwrite
```

* [git汉化](https://blog.justtodo.com/tool/git_setup/): 插件
* [印象笔记剪藏](https://www.yinxiang.com/webclipper/?downloaded)
* [安装自动提示命令](https://www.jianshu.com/p/0d265d9f914b)
```bash
  git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
  # 在~/.zshrc 中添加
  plugins=(
    zsh-autosuggestions
  )
```

* 安装语法高亮
```bash
  # if use brew install
  brew install zsh-syntax-highlighting
  echo "source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc

  # use git install
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
  echo "source \$ZSH_CUSTOM/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc
```

# 其它
* [Google Chorme 服务助手](https://ghelper.net/)：记得要登陆才会生效哦
* 更新.zshrc
```bash
  export http_proxy=http://127.0.0.1:1087;
  export https_proxy=http://127.0.0.1:1087;
安装更多brew
  brew install git --with-gettext  # 重启终端生效，同时安装英文版参考2，设置配置参考3
  brew install enca  # 批量文件格式转换工具，使用方法：enca -L zh_CN -x UTF-8 *
  brew cask install postgres pgadmin4  # pg客户端
  brew cask install sourcetree
  brew cask install  homebrew/cask-versions/docker-edge  # docker服务端，因内置compose版本太低弃用
  brew cask install qq wechat wechatwebdevtools
  brew cask install virtualbox vagrant vagrant-manager
  brew cask install chrome-remote-desktop-host
```

* sogouinput需要按提示进入目录安装
* google需要登陆才能同步收藏夹
* [docker加速配置](https://www.daocloud.io/mirror)

# 双系统
在mac中安装windows,个人机器目前只支持windows 10
* bootcamp菜单栏中下载windows支持软件，以便安装window下的所有驱动: `有时安装后会显示有此支持软件的安装盘`
* 原来已经安装了双系统：
  * 进入"磁盘工具”，选中”windows"所在的盘，执行“抹掉"
  * 运行”启动转换助理“bootcamp，按提示操作

# 参考
* [苹果官网问题咨询](https://getsupport.apple.com/?caller=home&PRKEYS=)
* 出现[此文所述错误](https://www.jianshu.com/p/7d055bebab46)，使用brew install brew-cask-completion代替
* 安装时如有卡住(更新需要翻墙)，按CTRL + C,不影响安装
* brew使用指南
```bash
 brew info         # 显示软件信息（包括安装参数说明)
 brew update       # 更新brew
 brew outdated     # 检查哪些软件需要更新
 brew upgrade      # 更新所有软件
 brew cleanup      # 清理不需要的版本极其安装包缓存
 brew install caskroom/cask/brew-cask  # 出现错误参考1
 brew cask search  # 显示所有可安装软件
```

# 工具
* Mounty
  1. 使用Mounty出现如下错误的[解决办法](http://yangl.net/2017/05/15/mounty_error/)：在windows下执行chkdsk /f
`The volume UNTITLEDis not re-mountable in read/write mode .Probably it was not clean unmounted before.`
  2. 外接硬盘文件为灰色时执行：xattr -d com.apple.FinderInfo *

* Unclutter
剪切板、处理中文件和临时笔记三合一管理的破解版，不要去升级，否则要收费

* [DictUnifier](https://www.jianshu.com/p/c57be986589b): 词典转换工具
推荐词典: 朗道英汉字典5.0
* [USB转串口驱动程序](https://www.prolific.com.tw/US/index.aspx), 注意Mac OS High Sierra 10.13上安装时[Blocked kernel extension的问题](https://developer.apple.com/library/archive/technotes/tn2459/_index.html)
* 远程操作

以下软件可以通过brew安装
* [MicrosoftRemoteDesktop](https://blog.csdn.net/ytangdigl/article/details/78941783): 远程桌面登录到windows
* shuttle: 简易SSH快捷菜单
* [coolterm](https://blog.csdn.net/bht890811/article/details/74151180): 串口调试助手/[minicom](https://blog.csdn.net/u010285246/article/details/72354038): 串口调试工具
