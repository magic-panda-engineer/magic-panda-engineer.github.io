---
title: Azure 的 Computer Vision 程式範例 
date: 2020-05-18 00:25:39
categories:
- AI
tags:
- Computer Vision
- Azure Cognitive Service
- Azure 認知服務
---

現在 AI 影像辨識已經很成熟了，各大軟體廠都有提供相關的服務可以使用。

今天要介紹的是微軟 Azure Cognitive Service 之下的 Computer Vision。

這個服務是有免費額度的，這篇文章就帶大家一步一步的寫 Azure Computer Vision 的程式吧！

<!-- more -->

[不過首先，要先做好 Azure Computer Vision 的設定，可以參考這篇文章。](https://magic-panda-engineer.github.io/AI/Azure-Computer-Vision-Tutorial.html)

# 程式撰寫

## 建立主控台應用程式

打開 Visual Studio 2019，或是要使用其他的版本也可以。不過都2020年了，升級一下吧 XDDD。

接著我們建立新的專案，這邊我們選擇 .NET Core 的主控台應用程式。

---

## 安裝必需套件

我們打開 NuGet 套件管理員，輸入 `Microsoft.Azure.CognitiveServices.Vision.ComputerVision`

我們要安裝的就是這個套件。

如圖所示，第一個就是了。

記得選擇穩定版的，比較不會有意外狀況發生。

![Azure Cognitive Service Computer Vision Program](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv1.png)

---

## 開始寫程式

還記得[這篇文章](https://magic-panda-engineer.github.io/AI/Azure-Computer-Vision-Tutorial.html)中，談過的 key 和 endpoint 嗎？

我們要把拿到 key 和 endpoint，用來建立連線：
```csharp
ComputerVisionClient client = new ComputerVisionClient(new ApiKeyServiceClientCredentials(key)){ Endpoint = endpoint };
```

接著建立主要的偵測影像的method，我們就用偵測色情圖片，來測試Computer Vision這個服務的威力吧：
```csharp
public static async Task DetectPorn(ComputerVisionClient client, string imgUrl)
{
    // 建立回傳的features的list，這裡使用Adult
    List<VisualFeatureTypes> features = new List<VisualFeatureTypes>()
    {
        VisualFeatureTypes.Adult
    };

    Console.WriteLine($"分析圖片 {imgUrl}...");
    Console.WriteLine();

    ImageAnalysis results = await client.AnalyzeImageAsync(imgUrl, features);

    //分別列出成人內容和猥褻內容
    Console.WriteLine($"含有成人內容: {results.Adult.IsAdultContent} 可信度 {results.Adult.AdultScore}");
    Console.WriteLine($"含有猥褻內容: {results.Adult.IsRacyContent} 可信度  {results.Adult.RacyScore}");
    Console.WriteLine();
}
```

## 測試結果

我們把要測試的圖片的 URL，送給這個 method，就可以來判斷這個圖片是不是色情圖片啦！

請看這個截圖，為了避免問題，我把色情圖片的 URL 剪掉了，大家可以自行找圖來測試。

可以看到，我們剛剛的測試照片，真的被判定為成人內容呢！

![Azure Cognitive Service Computer Vision Program](https://magic-panda-engineer.s3-ap-northeast-1.amazonaws.com/blog-img/20200517-azure-cv8.png)


## 描述圖片的功能

也可以使用 `VisualFeatureTypes.Description`，來描述這張圖片的內容：
```csharp
List<VisualFeatureTypes> features = new List<VisualFeatureTypes>()
{
    VisualFeatureTypes.Adult, VisualFeatureTypes.Description
};
```

然後再加上：
```csharp
Console.WriteLine("圖片描述:");
foreach (var caption in results.Description.Captions)
{
   Console.WriteLine($"{caption.Text}");
}
```

天啊，這個圖片描述太可怕了，不便放上來，大家就自己測試吧（怕.jpg


## 其他Computer Vision的功能

其他還可以取得 `Categories`，`Tags`，`Objects`，`Brands`，`Faces`等等的功能。

只要把這些選項，放在範例程式碼的 `features` 中，就可以再多辨識影像其他的內容囉！

舉例來說，你要做物件偵測，那麼就可以加入 `VisualFeatureTypes.Objects`，就能做物件偵側啦！

這個物件偵測，我們之後可以再寫一篇。

---

最後大家應該會要問，什麼是成人內容，什麼是猥褻內容呢？

根據微軟的文件，成人內容是指裸體和性行為的內容，而猥褻內容是具有暗示性的影像。

大家可以試著放比基尼相關的照片，看結果就知道兩者之間的差異了。

另外還有一個新的是 `isGoryContent` ，這個是血腥的內容。

不過我這麼純真善良、連冰與火之歌都不敢看的工程師，就先來測試血腥內容的照片啦！


**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**