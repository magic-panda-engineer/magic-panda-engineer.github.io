---
title: 解決 Hexo Searchdb 不能使用的問題
date: 2019-04-19 23:56:02
categories:
- Hexo
tags:
- Hexo searchdb
---

有一天，突然Hexo的searchdb插件不能用了！！

點擊搜尋後，會顯示載入中的動畫，可是一直都沒有載入 orz

Hexo的搜尋文章功能，是建立一支xml檔上面的，叫做`search.xml`

<!-- more -->

打開瀏覽器，進入到這個xml檔的路由，看看到底發生什麼事情：`localhost:4000/search.xml`

這時候畫面居然提示：`Input is not proper UTF-8, indicate encoding !`

怎麼可能會有非UTF-8的特殊字元呢@@？

查遍了所有文章，都找不到非UTF-8的字元，真的是非常的神奇。

## 解決方法

這時候突然靈機一動，想說會不會是VS code沒有顯示出非UTF-8的字元。

於是用Sublime text打開專案，果然就在字裡行間發現了一個東西長成這樣`<0x40>`。

也不知道怎麼冒出這個這東西的，總之刪掉了就好了…… orz


如果你Hexo searchdb的功能也不能用的話，試試看這招吧！


**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**