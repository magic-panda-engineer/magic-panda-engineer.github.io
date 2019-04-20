---
title: CSS Flex筆記--從六角學院的遊戲出發
date: 2019-04-20 21:07:10
categories:
- CSS
tags:
- css flex
---

最近玩了六角學院出的[CSS Flex的遊戲](https://hexschool.tw/flexGame)

雖然自從Bootstrap 4 出來之後，就開始有在用Flex排版。

但是畢竟依賴框架的下場就是原生的寫法不甚熟悉。

<!-- more -->

不過沒沒有想到花了半個小時，就破全關了。等於一個關卡1.5分鐘。

某位前端高手好友，也差不多是這個數字，表示我寫CSS的功力還算可以啦 XDDD

倒是六角學院的社團內一堆十分鐘左右破關的妖魔鬼怪，真的是前端人材濟濟。

![半小時破全關](https://s3-ap-northeast-1.amazonaws.com/magic-panda-engineer/blog-img/20190420-css-flex.png)


# CSS Flex排版

看完這篇就能幾乎掌握CSS Flex排版啦！！

Flex是CSS3之後推出的，主要為了適應不同螢幕尺寸和設備而誕生的排版方法。

因此已經不用再使用`Float`排版啦！

## 1.先設定Flex排版

**一開始要先設定一個Flex排版，不然Flex相關的屬性都會吃不到的。**

```css
.my-flex {
  display: flex;
}
```


## 2.Flex可以設定排版方向 -- flex-direction

可以設定欄與列的排版方向，光這是一點就打爆古早`Float`的寫法啦！！

如果不設定的話，default是`row`。

Flex-direction的效果可以到這個[網頁去試玩](https://www.w3schools.com/cssref/playit.asp?filename=playcss_flex-direction)。

```css
.my-flex {
  display: flex;
  flex-direction: row|row-reverse|column|column-reverse|initial|inherit;
}
```

## 3.元素超出螢幕範圍時是否換行 -- flex-wrap

如果選擇`no-wrap`的話，就會把所有的元素都擠在同一行裡。

`no-wrap`做某些表格類型的呈現，但又不是表格的特別好用 XDD。

[一樣可以到W3School去試玩](https://www.w3schools.com/cssref/playit.asp?filename=playcss_flex-wrap)

```css
.my-flex {
  display: flex;
  flex-wrap: nowrap|wrap|wrap-reverse|initial|inherit;
}
```


## 4.把direction 和 wrap 二合一 -- flex-flow

用`flex-flow`可以只寫一行，就把direction 和 wrap 二合一。

第一個參數direction，第二格是wrap。**注意中間用空格隔開。**

```css
.my-flex {
  display: flex;
  flex-flow:row-reverse nowrap;
}
```

## 5.元素對齊的方式之一 -- justify-content

`justify-content`是元素對齊的方式，可以簡單地把它當成**水平排版**的方式。

**最常用到的功能就是水平置中啦！！**

[一樣可以到W3School去試玩](https://www.w3schools.com/cssref/playit.asp?filename=playcss_justify-content)

```css
.my-flex {
  display: flex;
  justify-content: flex-start|flex-end|center|space-between|space-around|initial|inherit;
}
```

## 6.元素對齊的方式之二 -- align-items

`align-items`是元素對齊的方式，可以簡單地把它當成**垂直排版**的方式。

**最常用到的功能就是垂直置中啦！！**

(垂直伸展`stretch`其實也還滿常用的到的啦)

[一樣可以到W3School去試玩](https://www.w3schools.com/cssref/playit.asp?filename=playcss_align-items)

```css
.my-flex {
  display: flex;
  align-items: stretch|center|flex-start|flex-end|baseline|initial|inherit;
}
```

## 7.多行元素對齊的方式 -- align-content

`align-content`是多行元素對齊的方式。

**注意這個屬性要加上`flex-wrap`才能使用哦！！**

[一樣可以到W3School去試玩](https://www.w3schools.com/cssref/playit.asp?filename=playcss_align-content)

```css
.my-flex {
  display: flex;
  align-items: stretch|center|flex-start|flex-end|baseline|initial|inherit;
}
```

---
**到此為止，已經學完CSS Flex的排版啦！！**
**接下來要來看CSS Flex個別子元素的排版啦！！**

---

# CSS Flex個別子元素的排版

一個Flex容器內的各個子元素，都還可以獨立再做排版的。

## 1.個別子元素的對齊 -- align-self

`align-self`是針對個別子元素的對齊調整，只要注意該子元素的外層是`flex`即可。

[一樣可以到W3School去試玩](https://www.w3schools.com/cssref/playit.asp?filename=playcss_align-self)

```css
.my-flex {
  display: flex;
}

//外層是.my-flex
.my-flex1 { 
  align-self: auto|stretch|center|flex-start|flex-end|baseline|initial|inherit;
}
```


## 2.個別子元素的寬度 -- flex-grow & flex-shrink

`flex-grow & flex-shrink`是針對個別子元素的寬度調整，望文生義即可知道為寬度增加和減少。

要注意該子元素的外層是`flex`。

[到W3School去試玩flex-grow](https://www.w3schools.com/cssref/playit.asp?filename=playcss_flex-grow)
[到W3School去試玩flex-shrink](https://www.w3schools.com/cssref/playit.asp?filename=playcss_flex-shrink)

```css
.my-flex {
  display: flex;
}

//外層是.my-flex
.my-flex1 { 
  flex-shrink:8;
}

.my-flex2 {
  flex-grow:8;
}
```


**以上就是CSS Flex常用到的排版技巧啦！！**


**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**