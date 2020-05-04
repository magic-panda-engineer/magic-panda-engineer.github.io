---
title: 討論用 Azure Bot Service 開發 LINE bot
date: 2020-01-04 18:47:14
categories:
- ChatBot
tags:
- LINE bot
- LIFF
- Azure
- LUIS
- NLP
---

近幾年 Line 聊天機器人爆紅，許多軟體工程師多少都會碰到聊天機器人的需求。

為了讓聊天機器人開發更方便，微軟推出了一項非常強大的工具：Azure Bot Service。

我試玩了Azure Bot Service之後，想來分享一些LINE bot開發心得。

<!-- more -->

Azure Bot Service 是微軟推出的一項聊天機器人服務，如其名是建構在 Azure 上面的一項雲服務。

可用於輪替簡單、重複性工作，例如預訂晚餐或蒐集設定檔資訊。 

使用者可使用文字、互動式卡片和語音來與 Bot 交談。 

和 Bot 互動可以是快速的問與答，用 Rule-base 的方式來建立簡單規則。

也可以配合使用 LUIS ，建立複雜的對話機制。

總而言之，和聊天對話相關的，我們都可使用 Azure Bot Service 很輕鬆的辦到。

---

現今市場上的 Line Bot，多是以 LINE Front-end Framework (LIFF) 為主的方式來呈現的。

LIFF 簡單來說，就是做一個網站在 Line Bot裡面，透過 Line 的 library 和網站做互動。

同時也會搭配 Rich Menu 、ImageMap 等方式來呈現，讓使用者只需要點擊按鈕就可以達到使用目的。

Azure Bot Service 裡面也是有提供了類似的功能，如互動式卡片之類的，也是可以串接到 Line 上面。

Azure Bot Service 裡面，也包含了一個 app serivce。 

App service 就是一個host服務，可以部署你的網站上去。因此我們就可以用 LIFF 的方式，來製做我們的 Line Bot。

---

有了LIFF、Rich Menu、ImageMap 等等和 user 互動的形式，使用自然語言對話的場合就比較少了一些了。

終究打字還是會比按按鈕來得麻煩一些。

但是如果真的有需要使用自然語言對話的方式來和客戶互動，例如客服之類的bot，就可以使用微軟的自然語言工具 Language Understanding Intelligent Service (LUIS) 來達成。

當然 Azure Bot Service 可以開一個 LUIS 起來做串接。

---

總之，Azure Bot Service 包含了許多現在開發 Line Bot 很重要的幾項功能，真的很不錯。

我當年做通勤學的時候，只用了一個 app service，幹出了一大堆功能，現在想想真的血汗 XDDD 。


---



**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**