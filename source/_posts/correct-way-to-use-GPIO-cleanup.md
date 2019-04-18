---
title: 正確使用GPIO cleanup()方式
date: 2019-04-16 20:38:25
categories:
- RaspberryPi
tags:
- IOT
- GPIO
- Python
---

在以Python寫樹莓派GPIO的時候，範例程式常常會在最後一行加上` GPIO.cleanup()`，讓程式結束時可以把GPIO的設定清掉。

最近在開發時，發現明明都已經加上了` GPIO.cleanup()`，但是設定還是都清不掉……。

GPIO一旦沒有清掉，在跑同一隻程式時，會出`RuntimeWarning: This channel is already in use, continuing anyway.  Use GPIO.setwarnings(False) to disable warnings.
` 這樣子的一段警告。

<!-- more -->

此時只能重新開機，才能重置GPIO。可是重新開機很麻煩啊，該怎麼辦呢？



## 問題點在哪裡？

首先我們先來看看問題點在哪？

一般的範例程式，都是這麼寫的：

``` python

while True:
    
    GPIO.output(LED_PIN, GPIO.HIGH)
    print("燈亮啦！")

GPIO.cleanup() 

```

上面的程式碼，明明在最後一行加上了 `RuntimeWarning: This channel is already in use, continuing anyway. `

可是按下 CTRL + C 中止之後，再跑一次程式，還是會得到 `RuntimeWarning: This channel is already in use, continuing anyway.` 的警告

**因為 GPIO.cleanup() 在 while 迴圈外，所以根本不會執行到啊！！**


## 解決方法

那麼我們該如何解決呢？

只要善用例外處理的 try except finally 的技巧，就可以讓 `GPIO.cleanup()` 順利運作啦。

正確使用`GPIO.cleanup()`方式的範例如下：

``` python
try:
    
    while True:
        
        GPIO.output(LED_PIN, GPIO.HIGH)
        print("燈亮啦！")
    
except KeyboardInterrupt:  
    # 當你按下 CTRL+C 中止程式後，所要做的動作
    print("STOP")
  
except:  
    # 其他例外發生的時候，所要做的動作
    print("Other error or exception occurred!" )
  
finally:  
    GPIO.cleanup() # 把這段程式碼放在 finally 區域，確保程式中止時能夠執行並清掉GPIO的設定！
```


**如果這篇文章有幫助到你，歡迎在下方disqus留言版按愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**