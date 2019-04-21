---
title: Hexo Next主題加上最近文章版面
date: 2019-04-21 15:47:00
categories:
- Hexo
tags:
- Hexo Next theme
---

當初會選擇Next這個主題，就是看在它黑白分明配色，相當符合熊貓的主題。

用了一陣子後發現，這個主題居然沒有最近文章的版面。

沒有的話，就只好自己動手做啦！

<!-- more -->

雖然不會寫swig，不過大概就是和ejs很像的東西吧

## 具體步驟

1. 打開`next/layout/_macro/sidebar.swig`

2. 找個喜歡的地方，貼上下列程式碼。（我是貼在`if theme.links`的前面）

```html
{% if theme.recent_posts %}
<div class="links-of-blogroll motion-element {{ "links-of-blogroll-" + theme.recent_posts_layout  }}">
<div class="links-of-blogroll-title">
    <!-- 設定你要的fa fa icon-->
    <i class="fa fa-history fa-{{ theme.recent_posts_icon | lower }}" aria-hidden="true"></i>
    {{ theme.recent_posts_title }}
</div>
<ul class="links-of-blogroll-list">
    {% set posts = site.posts.sort('-date') %}
    {% for post in posts.slice('0', '5') %}
    <li>
        <a href="{{ url_for(post.path) }}" title="{{ post.title }}" target="_blank">{{ post.title }}</a>
    </li>
    {% endfor %}
</ul>
</div>
{% endif %}
```

3. 在主題的設定文件`hexo/themes/next/_config.yml`，加上下列參數。

```js
recent_posts_title: 近期文章
recent_posts_layout: block
recent_posts: true
```

4. 使用指令重建hexo，就可以看到近期文章的區塊啦。`hexo clean && hexo g && hexo s`

---

**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**