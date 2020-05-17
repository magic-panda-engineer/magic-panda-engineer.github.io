---
title: Azure 的 Computer Vision 服務設定教學
date: 2020-05-17 20:33:50
categories:
- AI
tags:
- Computer Vision
- Azure Cognitive Service
- Azure 認知服務
---

現在 AI 影像辨識已經很成熟了，各大軟體廠都有提供相關的服務可以使用。

今天要介紹的是微軟 Azure Cognitive Service 之下的 Computer Vision。

這個服務是有免費額度的，這篇文章就帶大家一步一步的設定 Azure 吧！

<!-- more -->

## 第一步

首先進到 Azure Portal，找到 Azure Cognitive Service。

Azure Cognitive Service 中文叫做認知服務，如果是用中文版 Azure 的朋友可以用認知服務這個詞來找。

![Azure Cognitive Service Computer Vision](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv2.png)

---

## 第二步

點進到 Azure Cognitive Service 之後，可以看到這項服務的 dashboard。

如果之前有新增過服務的話，也會出現在列表上面。

進到這個畫面後，我們點擊左上角的 Add。

![Azure Cognitive Service Computer Vision](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv3.png)

---

## 第三步

接著會進到 Marketplace 裡面，這裡有許多 Azure Cognitive Service 相關的服務。

也有一些是第三方廠商上架的服務，整個和 AWS 很像。

這時候在上方的搜尋bar裡，輸入computer vision，中文的使用者可以輸入電腦視覺。

這時候跳出的第一個選項，就是我們要的服務囉！

![Azure Cognitive Service Computer Vision](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv4.png)

---

## 第四步

點擊 Marketplace 出來的第一個computer vision之後，就會進到這個頁面，這時候選擇紅色框框起來的Create。

![Azure Cognitive Service Computer Vision](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv5.png)

---

## 第五步

這時候我們就來做設定啦！ 請看圖片

第一個 Name 會決定你endpoint URL，所以要是唯一的。

第二個 Subscription 就選擇免費版的，或是免費已過期就用付費版的訂閱。

第三個地點，就盡可能選離你服務比較近的地方，台灣可以選Japan East。

第四個 Pricing Teir，選免費的額度，會有每分鐘20個呼叫、每月5000個呼叫的額度。

第五個 Resource group 就選擇您想要的資源群組吧！要新建一個也是可以。

最後按下 Create。

![Azure Cognitive Service Computer Vision](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv6.png)


---

## 第六步

Create 點下去之後，需要等待一段時間。

等創建完成了之後，我們點擊進來剛剛創建的資源，就會可以看這個 computer vision 服務 dashboard 了。

大家可以在這個頁面探索一下，有哪些可以操作的。

不過我們直接接入重點，請點擊左方選單的 Keys and Endpoint。

點進去後，我們就可以看到如圖所示的 Key1 、 Key2，還有 Endpoint 了。

![Azure Cognitive Service Computer Vision](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv7.png)


Key1 Key2都可以做為連結到這個 Computer Vision 服務的key。

也可以點擊圖片中的 Regenerate 按鍵，來產生新的key。

---

## 最後一步

Azure Computer Vision 設定就到此結束啦！！

記下這個 key 和 endpoint，下一步我們就可以開始寫程式了。

[關於程式的教學與說明，就請移駕到這篇文章。](https://magic-panda-engineer.github.io/AI/Azure-Computer-Vision-Program-Sample.html)


**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**