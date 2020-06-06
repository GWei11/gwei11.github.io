---
title: hexo
categories:
  - 博客
tags:
  - hexo
abbrlink: ab21860c
---
# 文章目录默认展开

[参考文章](https://blog.csdn.net/wugenqiang/article/details/88609066)

对于想要通过点击目录来进行展开与收缩的，需要进行下面的操作，把

```
//文章目录默认展开
.post-toc .nav .nav-child { display: block; }
```

里面的`.nav-child`去掉即可通过点击来实现目录的展开与收缩。

<!--more-->

# 新建菜单以及添加菜单图标

[next官网](http://theme-next.iissnan.com/getting-started.html#menu-settings)

在官网中查看主题设定->菜单那部分，当我们新添加一个菜单是(比如我要添加阅读)，在`next`的配置文件中(`_config.yml`)里面找到下面的配置：

```
menu:
  home: / || home
  tags: /tags/ || tags
  categories: /categories/ || th
  archives: /archives/ || archive
  book: /book || book #这里是新添加的菜单

# Enable/Disable menu icons.
menu_icons:
  enable: tru
  book: book（这里是图标）
```

然后在开启的对应的语言文件中，比如我使用的是中文，那么就是在`zh-Hans.yml`文件中找到`menu`：

```yml
menu:
  home: 首页
  archives: 归档
  categories: 分类
  tags: 标签
  search: 搜索
  book: 阅读
```

后面的book那一栏是后来添加的。需要注意的是在上面的第一个配置文件中所写的`book`是[Font Awesome](http://fontawesome.io/)中`icon`的名称，这样才可以在我们自己的页面显示出图标。

# 添加社交功能之邮箱

在next主题配置文件搜索social:

```yml
social:
  E-Mail: mailto:1744709138@qq.com || envelope
```

这里只是显示了邮箱，这些原来都是注释掉的，自己去掉前面的注释即可，需要注意的是邮箱前面的`mailto`是必须要保留的，还有最后面的`envelope`则是图标名字，也是不能修改的。

# 友情链接的配置

在`next`主题配置文件中查找标签`links`并进行如下配置:

```yml
# title
links_title: Links
links:
  MacTalk: http://macshuo.com/
  Title: http://example.com/
```

# 实现聊天功能

[查看转载文章](https://hoxis.github.io/hexo-next-daovoice.html)

# 添加近期文章展示

[查看转载文章](https://blog.csdn.net/wugenqiang/article/details/88581218)

# 显示文章的更新时间

在主题的配置文件中找到`updated_at`，然后将其值修改为`true`即可(这种方式应该是适用于5以后的版本)

对于以前的方式可以看这篇[别人写的文章](https://blog.csdn.net/ganzhilin520/article/details/79053399)

# 字数统计与阅读时长

[查看转载文章](https://www.cnblogs.com/php-linux/p/8418518.html)

# 添加版权信息

在站点配置文件搜索`post_copyright`，将`enable`修改为`true`，添加`author`即可。

```yml
post_copyright:
  enable: true
  license: CC BY-NC-SA 3.0
  license_url: https://creativecommons.org/licenses/by-nc-sa/3.0/
  author: 咖啡杯里的茶
```

# 修改文章底部的标签

修改模板 `/themes/next/layout/_macro/post.swig`，搜索 `rel="tag">#`，将 # 换成`<i class="fa fa-tag"></i>`

# 修改博客的背景图

在`themes->next->source->css->_custom->custom.styl`添加如下的代码:

```css
//背景图
body { 
    background-image: url(https://i.loli.net/2019/05/02/5ccab829cdad9.jpg);
    background-attachment: fixed; // 不随屏幕滚动而滚动fixed,scroll,inherit
    background-repeat: no-repeat; // 如果背景图不够屏幕大小则重复铺，改为no-repeat则表示不重复铺
    background-size: cover; // contain等比例铺满屏幕 //cover拉伸铺满
    background-position: bottom;//x,y轴调整
    +mobile(){
      //background-position: 0% -20%;https://i.loli.net/2019/05/02/5ccab829cdad9.jpg
      //https://i.loli.net/2018/12/29/5c270fc2bfcad.png
      background-image: url(https://i.loli.net/2019/05/02/5ccab829cdad9.jpg);
      background-size: cover;
    }
}
```

上面几个有`url`的地方换成自己想要使用的背景图的图片的外链地址即可。

# 将文章归类到新建的菜单中

比如自己已经添加了新的菜单`book`，现在想要将新建的文章归类到`book`这个菜单下做法如下：

在menu下如下配置：

```xml
menu:
    home: / || home
    tags: /tags/ || tags
    categories: /categories/ || th
    archives: /archives/ || archive
    book: categories/book || book
```

最后一个book是我自己新建的分类。然后再写文章时添加如下头部信息:

```xml
title: abc
categories:
  - book
```

这样当你点击`book`那个菜单时就会先显示`abc`这篇文章。

[参考链接](https://www.cnblogs.com/codebook/p/10312965.html)



# 显示图片

[显示图片](https://www.jianshu.com/p/ea78bdd0551f)

# 添加搜索功能

[添加搜索](https://blog.csdn.net/qq_40265501/article/details/80030627)

# 添加打赏功能

在`next`主题的配置文件文件中加上下面的代码

```xml
reward_comment: 坚持原创技术分享，您的支持将鼓励我继续创作！
wechatpay: /images/微信支付.jpg
alipay: /images/支付宝支付.jpg
```

其中`wechatpay`和`alipay`对应的是微信支付收款码和支付宝支付收款码的图片地址，我这里是存放在 `主题\source\images\`下面