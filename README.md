# Blog-Jekyll

复制于唯一一篇 `post.md`

本篇用最通俗易懂的方法介绍如何用 Jekyll 和 GitHub 搭建一个简单小巧的个人博客。

其实想开博客的想法存了有一两年了，我其实不是很擅长写文章，就连流水账到最后也坚持不下来。前期入过手账坑，一股脑儿地买过好多胶带和贴纸。手账断更之后，因为在工作中为公司的博客写过 wordpress 主题，所以有打算用 wordpress 自己设计一套主题，可是万万没想到，等我做完项目我就再也不想看到 wordpress 了（原因自行脑补）。最后打算用 Jekyll 主要因为支持 markdown 和 Sass 并且真的很简单，而且通过 GitHub 管理也很方便。

**Prepare**

创建步骤、介绍、文件结构就不列了，附上 [Jekyll](http://jekyllrb.com/) 和 [GitHub Pages](https://pages.github.com/) 官网链接。

**\_config.yml**

配置文件中主要包含这么几大部分：博客信息、个人信息、菜单配置、社交信息、菜单配置、路由信息和一些其他的配置（根据实际情况取舍）

**Category & Tag**

1. 首先保证 `_posts` 中的文章有类别 categories 和 tag 属性，如果有多个属性或者标签写成 `tag: [jekyll, blog]` 的形式。

2. 在 `_layouts` 中添加两个模版文件，分别为：`blog_by_category.html` 和 `blog_by_tag.html`。

3. 在博客项目的根目录下新建一个文件夹叫做 `blog`，包含 `category` 和 `tag`两个子文件夹。

4. 对应分类与标签页的路由：`blog/category/jekyll/`、`blog/tag/jekyll/`，每个分类和标签页都生成了单独的静态页面。

5. 在首页中显示分类信息和标签内容：(去掉%前面的/)，具体内容可以在项目里面看到。

**Comment**

先通过 [DISQUS](https://disqus.com/) 注册账号，然后在 `post.html` 模版对下面加上这么一段代码：

```
<div id="disqus_thread"> </div>
    <script type="text/javascript">
        /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
        var disqus_shortname = 'cenalulu'; // required: replace example with your forum shortname
        /* * * DON'T EDIT BELOW THIS LINE * * */
        (function() {
            var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
            dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
            (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
        })();
    </script>
    <noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
</div>
```

**Date**

不同的日期格式： `page.date | 替换部分`

`date_to_string`: 05 Apr 2016

`date_to_long_string`: 05 April 2016

`date: "%b %-d, %Y"`: Apr 5, 2016

`date:"%B %d, %Y"`: April 05, 2016

`date: "%Y-%m-%d"`: 2016-04-05

`date: "%m/%d/%Y"`: 04/05/2016

`date: "%-m/%-d/%Y"`: 4/5/2016

这里只列了几种常用的，其他更多的日期格式可以参考 [Jekyll Date Formatting Examples](http://alanwsmith.com/jekyll-liquid-date-formatting-examples)

**Theme**

本博客的主题的主题色是：<span style="display: inline-block; width: 12px; height: 12px; background-color: #92b34c;"></span> #92b34c <span style="display: inline-block; width: 12px; height: 12px; background-color: rgba(146, 179, 76, .6); margin-left: 20px;"></span> 60%  <span style="display: inline-block; width: 12px; height: 12px; background-color: rgba(146, 179, 76, .2); margin-left: 20px;"></span> 20%

Markdown 的样式参考 [sindresorhus/github-markdown-css](https://github.com/sindresorhus/github-markdown-css)，在此基础之上做了一些调整。

写这篇文章的时候我猛然发现我的设计稿已经不见了……肯定被我清文件的时候误丢到垃圾桶里了！！！

 (╯°□°）╯︵ ┻━┻

不过没事，我还有仅存的两张 jpg（捂胸口

在搭建博客之前没有考虑 markdown 的主要标签的样式，所以建议大家先搭再设计。

ps: (这里放第一版的设计图，完成日期：2016年3月3日)

![博客文章内页](http://7xso7u.com2.z0.glb.clouddn.com/Blog%20Post%20.jpg)

![博客首页](http://7xso7u.com2.z0.glb.clouddn.com/Blog%20Index%203.13%2018:00.jpg)

### 变幻莫测的人生啊

6号下午决定不用 Jekyll 了，因为我突然发现有比 Jekyll 更好的了。。。（我真的不是善变

但是之前写的这篇文章，源文件（半成品）还是决定挂出来，不知道能不能有帮助？

另外这个设计的主题有喜欢的就拿去用吧 :D

### DISQUS 的坑

关于 DISQUS 的 shortname，shortname 和 name 和 username 都不一样！！！都不一样！！！都不一样！！！

只简单注册完了的用户，在右上角头像处可以看到有一个 Add Disqus to Site，需要走完所有流程，这里设置的 shortname 才是需要。

Site 建成功后，右上角菜单里才有 Admin 这个选项。

```
var disqus_shortname = 'h2so4';
```

