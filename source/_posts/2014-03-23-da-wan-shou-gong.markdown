---
layout: post
title: "搭建octopress 打完收工"
date: 2014-03-23 18:21:32 +0800
comments: true
categories: [tools, opensource]
tags: [octopress]
---

##搭建octopress
搭建了这个blog，看了网上各位同学的文章，具体步骤我就不说了.
还是遇到了好几个问题。

##问题1 
 Error running 'requirements_osx_brew_libs_install autoconf automake
 libtool pkg-config libyaml readline libksba openssl'
遇到这个问题的解决办法就是用brew一个一个的install

ps:大家用homebrew的时候一定要删除自己的macport，不然会碰到各种诡异的冲突

##问题2
clang: error: unknown argument: '-multiply_definedsuppress'
[-Wunused-command-line-argument-hard-error-in-future]
clang: note: this will be a hard error (cannot be downgraded to a warning) in
the future
make: *** [redcloth_scan.bundle] Error 1

make failed, exit code 2

Gem files will remain installed in
/Users/hcy/.bundler/tmp/5760/gems/RedCloth-4.2.9 for inspection.
Results logged to
/Users/hcy/.bundler/tmp/5760/extensions/universal-darwin-13/2.0.0/RedCloth-4.2.9/gem_make.out
An error occurred while installing RedCloth (4.2.9), and Bundler cannot
continue.
Make sure that `gem install RedCloth -v '4.2.9'` succeeds before bundling.

这个问题出现在我使用2.0.0的ruby和xcode5.1环境下，解决方案是要安装手动去安装redcloth
，然后在命令行前面加入ARCHFLAGS=-Wno-error=unused-command-line-argument-hard-error-in-future


##总结
1 不要去动苹果自带的ruby

2 最好使用rvm来安装1.9.3，一路使用rvm来安装，这样会少的碰到各种错误


##最后
最近真的活挺忙的，博客就挑问题写了。回头为大家分享一些技术文章，共同进步。


