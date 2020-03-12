# 这是我的github博客.
## 分支
master: hexo生成的静态博客文件(这个是可以通过hexo的配置文件配置即可)
source(default): hexo的源文件(部署文件), 包括源码, package.json等
如果没有部署文件, 那么是无法恢复博客的, 也就是无法在新的电脑上提交博客

## 多台电脑上提交或者更新博客
包括恢复博客

直接git clone 博客地址 默认的就是部署文件分支, 因为这里面的才是我们需要提交修改的

然后如果是新的环境下 需要 npm install 安装相应的包

至此, 环境是OK的

## 发布或者修改文章
hexo new [layout] "title"

layout 是可选的, 默认是post, 可以在配置文件中修改. 此时在 /source/_posts/文件下, 生成了 title.md 的博客文件, 然后在 title.md 中修改编辑自己的博客文章即可, 语法是[MarkDown](https://www.runoob.com/markdown/md-tutorial.html)

hexo server 即可启动本地服务器预览文章

本地查看没问题后 执行<br />
hexo clean<br />
hexo generate<br />
hexo deploy<br />
分别是清理缓存, 生成静态文件, 部署到hexo上
可以写个脚本将这三个命令写进去

## 文章格式
### **1.添加"阅读全文"按钮**
添加
```c++
<!--more-->
```
这个标志上面的文字就会作为文章摘要显示
### **2.给文章添加分类和标签**
直接在 title.md 文件中设置tags和categories属性
```c++
title: 标题
date: 2020-03-12 14:31:10
tags:
- 博客           //多个标签可以这样添加
- hexo
categories: web前端
```
### **3.在博文中添加图片**
我的步骤如下:
* cd到博客根目录下 查看_config.yml文件 查找 post_asset_folder 字段确定post_asset_folder 设置为true -> post_asset_folder:true
* 当您设置 post_asset_folder 参数后，在建立文件时，Hexo 会自动建立一个与文章同名的文件夹，您可以把与该文章相关的所有资源都放到此文件夹内，这样就可以更方便的使用资源
* 到博客的根目录下执行 npm install https://github.com/CodeFalling/hexo-asset-image --save 命令来进行插件的安装
* 然后执行创建一文章时 hexo new "test" 然后查看博客的 /source/_posts 目录下的文件，会看到存在一个 test 文件夹 和 test.md 文件
* 将所需要的图片资源放到test 文件夹内 (test/dali.jpg)
* 书写文章使用test文件内的图片(dali/dali.jpg)
* hexo server 查看是否成功, 没问题后部署到线上即可


鸣谢 [在Hexo博客中发布文章](https://winney07.github.io/2018/08/02/%E5%9C%A8Hexo%E5%8D%9A%E5%AE%A2%E4%B8%AD%E5%8F%91%E5%B8%83%E6%96%87%E7%AB%A0/), 更多格式和方法请看这个博客, 上面写的是我常用的, 所以记录下.



