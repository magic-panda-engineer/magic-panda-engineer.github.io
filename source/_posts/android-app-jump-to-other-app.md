---
title: 用Intent在Android APP中打開其他app 
date: 2020-01-01 23:45:51
categories:
- Android
tags:
- Android Intent
---

Android開發者常常會碰到，在Android APP內打開其他APP的需求。

只要善用 Intent，就可以達成這個需求啦！

這段程式碼示範了如何打開其他的APP。

<!-- more -->

在客服的需求，很常會需要打開FB Messager，因此本篇示範如何打開FB Messager到特定的頁面。

注意你的手機需安裝FB Messager。

Uri.parse的部份可以可以自行替換成其他的APP Scheme，也就可以跳轉到其他APP了。


```java
try
{
    startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse("http://m.me/111417983616253")));
    //開啟大魔術熊貓工程師的粉絲專頁Messager
}
catch (ActivityNotFoundException ex)
{
    Toast.makeText(getContext(),
            "無法打開Facebook Messenger APP",
            Toast.LENGTH_SHORT).show();
}
```



**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**