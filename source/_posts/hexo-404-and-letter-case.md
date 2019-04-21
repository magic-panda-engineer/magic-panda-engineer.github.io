---
title: Hexo 404和字母大小寫的問題
date: 2019-04-21 09:43:40
categories:
- Hexo
tags:
- page 404
---

最近發現有些頁面會出現404，都是發生在點入特定的標簽或是分類時發生了。 

研究了一下，居然是因為字母大小寫的問題產生的 orz。像是分類如果寫CSS，和css，就會出現錯誤。

那麼我們要怎麼解決這個問呢？

<!-- more -->

## 解決方法 

在`.deploy_git`中，原始的設置是對大小寫不敏感的，可實際上大小寫不一樣就讓你404。

所以我們要修改`.deploy_git`中的設置。

1. 從Windows檔案總管或Mac Finder中打開專案中`.deploy_git`的資料夾。

2. 進到`.deploy_git`資料夾中`.git`，找到文件`config`。(用VS code可能會找不到.git資料夾)

3. 打開文件`config`，將 `ignorecase=true` 改為 `ignorecase=false`，存檔。

4. 把`.deploy_git`資料夾中除了`.git`之外的文件通通刪掉。

5. 再用指令`hexo clean && hexo g -d`，清除並佈署上去，就會發現404修好啦！


**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**