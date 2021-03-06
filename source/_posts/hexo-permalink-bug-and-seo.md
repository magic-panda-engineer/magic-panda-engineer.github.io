---
title: Hexo文件永久連結設定的BUG順便談SEO
date: 2019-04-18 17:33:53
categories: 
- Hexo
tags:
- SEO
---

永久連結(permalink)在SEO中是非常重要的因素，這關乎你的網站能不能被容易被排名到前面。

在設定Hexo的永久連結時，按照官方文件做，結果卻遇到一個bug。

這篇文章最後會分享怎麼解決這個問題。

<!-- more -->

## 先談時間格式和SEO

一個好的永久連結絕對不能超過三層，不然SEO的排名會比較後面。

像是`www.test.com/article/2019/01/01/page.html` 這種很多層的網址，就比較難有好的SEO表現。

（當然如果你這篇很多層的文章流量超高，SEO也是會排名比較前面啦！）


一般來說，網址會盡量不要超過三層，而日期這種型式的永久連結，就剛好會讓你網址超過三層。

再者，如果網址裡有日期的話，隨著時間的推移，Google漸漸下調你文章的排名。

雖然有的文章是不受時間影響的經典之作，但是就是Google的機制，也沒有辦法。

所以在設定Hexo永久連結時，建議要先把日期格式給改掉。


## 內容分類和SEO

如果一個網址長得像這樣 `www.test.com/cloths/men.html` ，一眼就能看出這個頁面的分類屬於服飾類，而且還是男裝。

Google的爬蟲也是一樣的，這種分類清楚的網址，特別容易有較好的SEO表現。

所以在設定Hexo永久連結時，建議使用分類的格式。 

而且文章的命名，也要清楚直接，讓人一看就知道這個網址可能是在講什麼主題。

記得字和字之間用dash `-` 來分開，不要用underscore `_`，Google有說過dash是比較好選擇。

**切記之後就不要再改文章分類了，不然會嚴重影響SEO**


## Hexo文件的BUG和解決之道

談完了以上的內容，就是要設定Hexo的永久連結啦！

按照文件，我要的永久連結格式是 `分類/文章名稱`，應該設定為 `:category/:title`

可是這樣子設定之後，卻沒辦法進去文章閱讀 @@

反而會將整個文章頁面下載下來，打開那個下載檔，裡面是該文章頁面的內容……。

要修正這個問題，只要將 `:category/:title` 改成 `:category/:title.html` 就可以啦！！

![如圖所示，加上`.html`即可](https://s3-ap-northeast-1.amazonaws.com/magic-panda-engineer/blog-img/20190418-hexo-doc-bug.png)
*如圖所示，加上`.html`即可*


**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**