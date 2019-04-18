---
title: 為什麼選用Hexo來寫部落格
date: 2019-04-18 16:24:09
categories: 
- Hexo
tags:
- Hexo Next theme
- Wordpress
- Static Site Generator
---

在Evernote寫技術筆記很多年了，最近因為想寫技術部落格，於是開始來尋找部落格的架站平台。

原本想說用熟悉的Wordpress，可是想到主機商的費用和搬遷的不便性，就決定使用時下最熱門的Static Site Generator啦！

目前Static Site Generator現在有三個最活躍的技術，分別是：**Jekyll、Hugo、Hexo**。

<!-- more -->
一開始在決定要用哪個技術時，其實考慮了很久。於是把各家的好壞都寫出來，讓大家參考。

## Jekyll的好與壞

Jekyll是Github自家品牌的Static Site Generator，有著強力後盾做為支援。

可是它是使用Ruby來達成的。

大家都知道Ruby在Windows環境下的支援度不太夠，雖然我是用Mac，但還是很常用Windows的環境來做開發。

再來是Ruby相對比較慢，看了許多部落格主的心得，文章多了之後，在建置網站時真的會花上幾分鐘的時間。

雖然後來**incremental regeneration**，能夠大幅加速，但是考量到常常使用Windows，加上和Ruby不熟，還是放棄它了。


## Hugo的好與壞

Hugo是用Go語言來達成的Static Site Generator，目前github上面的星星數已經超過Hexo了。

Hugo的特色是生成靜態網站的速度極快！官網號稱它是世界最快的！！

原本我一度就要使用Hugo來架站了，可是發現Hugo的插件和主題，相對比較少。

而且居然還沒有上到1.0版，反觀Hexo都3.8版了。

於是就暫時放棄使用Hugo啦，未來的某一天，Hugo更成熟的話，說不定會改用Hugo吧？


## Hexo的好與壞

Hexo是用Nodejs去完成的，生成的速度也是很快，不過的確還輸給Hugo一截。

實測Hugo1秒內就能建置完三篇文章的內容，Hexo要花4秒多。

雖然Hexo慢了一點，但是Hexo已經出來很多年了，周邊插件和社群活躍度都很高，主題選擇性也很廣。

而且我對於Nodejs相關的生態系比較熟悉，到時候要自己改些什麼東西也比較方便。

最後讓我選擇Hexo的臨門一腳，是Next這個主題，其配色是黑和白，相當符合大魔術熊貓工程師的意象 XDDD

附帶一提，Hexo是台灣人做的哦！在中國那邊的社群也是很活躍，因此中文資源也還滿多的。

---

以上就是三大Static Site Generator的分析啦！

接下來會再分享一些使用Hexo時踩到的坑。

**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**