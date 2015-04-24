title: "生命在于折腾"
date: 2015-03-23 17:04:08
tags: hexo github ubuntu10.04
---

捣鼓Hexo博客
折腾几个小时终于把hexo博客搞定，可以hexo deploy直接push到github上。
最开始打算用jekyll，发现我的老古董ubuntu10.04装rubygem，bundler这些都有问题，麻烦的很，干脆改搞hexo。
查了google百度发现因为hexo升级3.0很多都过时了，或者有些小问题，自己简单整理了一下，不走弯路，整个过程还是比较简单的。
1.首先安装nvm,因为需要Node.js,nvm安装我直接找的nvm的github按照上面的readme操作既可。
  nvm的github：https://github.com/creationix/nvm
  安装命令：
    #git clone https://github.com/creationix/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`
    #source ~/.nvm/nvm.sh
    #nvm install stable
    #nvm use stable
2.安装hexo
  这个参照hexo官网，还是官网靠谱。
  hexo官网：http://hexo.io/
    #npm install hexo-cli -g
    #hexo init blog(我是MyBlog)
    #cd blog
    #npm install(别遗漏这步)
    #hexo server(这条之后根据提示访问localhost:4000就可以看到第一个hexo页面了)
3.hexo的使用
  安装完就可以使用hexo写博客了。
  使用方法看hexo help基本就清楚了。
  首先是hexo new一个post
  然后编辑新建的post，在source/_posts目录下。
  编辑的话是markdown语法，什么插连接，代码块啊，图片啊网上随便搜搜就知道肿么弄了。
  最后就是hexo generate和hexo deploy。
  hexo generate比较简单，执行完生成public目录。
  比较麻烦的是hexo deploy，都是在这出问题。
  其实，deploy主要是写好_config.yml这个文件的deploy部分就好了。
  我的deploy部分：
deploy:
  type: git
  repo: https://yylzl@github.com/yylzl/yylzl.github.io.git
  branch: master
  需要注意的问题有以下几个：
  1)yml语法要求冒号后要有一个半角空格，没有的话貌似执行hexo deploy木有反应。
  2)hexo 3.0后type是git，之前是github。
  3)网上的一大堆ssh什么的根本不需要，repo写成git的remote就可以了。


  ~Duang，写这篇的时候发现hexo命令找不到了，source ~/.nvm/nvm.sh也不好使，查了半天发现nvm current是none，
  执行nvm use stable然后再source一下就OK了。
  最后，hexo命令都可以简写，只要单词首字母就可以。比如，hexo generate写成hexo g就可以。



