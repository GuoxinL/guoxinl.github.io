---
type: original
layout: post
title:  "MacOS 安装Jekyll"
categories: Jekyll
tags: MacOS Jekyll
author: Guoxin
---

* content
{:toc}

这是我的Blog的第一篇文章，也是在基于Github建立自己的Bolg碰到的第一个问题。

## 安装Ruby
在安装Jekyll之前需要先安装Ruby，没错就是那块红宝石在MacOS上安装很方便直接使用Homebrew即可。
在命令行下运行如下命令即可：

## 安装Jekyll

```zsh
sudo gem install jekyll
Fetching: safe_yaml-1.0.5.gem (100%)
Successfully installed safe_yaml-1.0.5
Fetching: rouge-3.3.0.gem (100%)
Successfully installed rouge-3.3.0
Fetching: forwardable-extended-2.6.0.gem (100%)
Successfully installed forwardable-extended-2.6.0
Fetching: pathutil-0.16.2.gem (100%)
Successfully installed pathutil-0.16.2
Fetching: mercenary-0.3.6.gem (100%)
Successfully installed mercenary-0.3.6
Fetching: liquid-4.0.3.gem (100%)
Successfully installed liquid-4.0.3
Fetching: kramdown-1.17.0.gem (100%)
Successfully installed kramdown-1.17.0
Fetching: ruby_dep-1.5.0.gem (100%)
Successfully installed ruby_dep-1.5.0
Fetching: ffi-1.10.0.gem (100%)
Building native extensions.  This could take a while...
ERROR:  Error installing jekyll:
	ERROR: Failed to build gem native extension.

    current directory: /Library/Ruby/Gems/2.3.0/gems/ffi-1.10.0/ext/ffi_c
/System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/bin/ruby -r ./siteconf20190427-4787-1o1r68s.rb extconf.rb
mkmf.rb can't find header files for ruby at /System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/lib/ruby/include/ruby.h

extconf failed, exit code 1

Gem files will remain installed in /Library/Ruby/Gems/2.3.0/gems/ffi-1.10.0 for inspection.
Results logged to /Library/Ruby/Gems/2.3.0/extensions/universal-darwin-18/2.3.0/ffi-1.10.0/gem_make.out
```
但是却报如下错误：
```zsh
ERROR:  Error installing jekyll:
	ERROR: Failed to build gem native extension.

    current directory: /Library/Ruby/Gems/2.3.0/gems/ffi-1.10.0/ext/ffi_c
/System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/bin/ruby -r ./siteconf20190427-4787-1o1r68s.rb extconf.rb
mkmf.rb can't find header files for ruby at /System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/lib/ruby/include/ruby.h

```
在stackoverflow上查询了一番后发现是因为没有安装Ruby开发头文件，在OSX上获取它们的最简单方法是安装XCode。  
链接：[When I try sudo gem install json I get the following error](https://stackoverflow.com/questions/761521/when-i-try-sudo-gem-install-json-i-get-the-following-error)  
执行以下命令即可：
```zsh
xcode-select --install
```
然后在执行Jekyll的安装命令就可以了
```zsh
sudo gem install jekyll
```

至此Jekyll的安装已经完成了。