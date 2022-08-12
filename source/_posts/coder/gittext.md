---
layout: post
title: gettext的使用
date: 2022-08-12 14:49
categories:
  - 技术
---

如何使用gettext呢？
<!-- More -->

1. 安装gettext
```bash
brew install gettext
brew link gettext --force
```

2. 创建本地化po文件
```bash
cat >hello.cxx <<EOF
// hello.cxx
#include <libintl.h>
#include <locale.h>
#include <iostream>
int main (){
 setlocale(LC_ALL, "");
 bindtextdomain("hello", ".");
 textdomain( "hello");
 std::cout << gettext("hello, world!") << std::endl;
}
EOF
xgettext --package-name hello --package-version 1.2 --default-domain hello --msgid-bugs-address="denley@justtodo.com" --output hello.pot hello.cxx
msginit --output-file hello.po --input hello.pot
```
可能需要输入邮箱地址，任意输入一个即可

3. 汉化内容: 可能替换不成功，直接修改即可
```bash
sed -e '/"hello, world!"/,/#: / s/""/"你好，世界!"/' hello.po
```

4. 测试
```bash
mkdir -p zh_CN/LC_MESSAGES
msgfmt --check --verbose --output-file zh_CN/LC_MESSAGES/hello.mo hello.po
g++ -o hello hello.cxx -lintl
./hello
```

# 参考
* [GNU gettext工具简介](https://www.atjiang.com/gnu-gettext-intro/)
