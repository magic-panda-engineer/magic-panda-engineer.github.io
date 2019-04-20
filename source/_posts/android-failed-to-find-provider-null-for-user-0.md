---
title: Activeandroid在SDK26之後會遇到的bug
date: 2019-04-19 22:26:29
categories:
- Android
tags:
- android-plugin
---

在Room出來之前，activeandroid是最受歡的ORM之一。

在業界還是很容易碰到維護案裡，使用activeandroid。

可是在Android SDK 26之後，activeandroid會出現一個bug。

<!-- more -->

會出現下列的錯誤訊息：
`Error saving model java.lang.SecurityException: Failed to find provider null for user 0; expected to find a valid ContentProvider for this authority
`


這時候要怎麼解決這個問題呢？

既然錯誤訊息說沒有contentprovider，我們就加一個上去吧！

打開專案的`AndroidManifest.xml`檔，在`aaplication` tag 之間貼上下列的程式碼，就可以修好這個bug啦！

``` xml
<provider
    android:name="com.activeandroid.content.ContentProvider"
    android:authorities="<你的專案package name>"
    android:enabled="true"
    android:exported="false">
</provider>
```




**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**