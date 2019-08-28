---
title: 用Python比較兩個list內容的差異
date: 2019-08-28 14:28:51
categories:
- Python
tags:
- Python
---

在整理資料的過程中，常常碰到兩個資料夾之中，裝有類似、但不完全一樣的檔案數量

例如說，同樣的檔案名稱，但是不同的副檔名（常見於深度學習的影像檔和標記檔）

這時候就會先把各類別的檔案名稱，存到各自的list之中

<!-- more -->

如果要比較兩個list之間的差異，就可以利用`set().symmetric_difference()`來完成：

```python
def Diff(li1, li2): 
    return (list(set(li1).symmetric_difference(set(li2))))


list1 = [1,2,3,4,5]
list2 = [5,6,7,8,9]

print(Diff(list1, list2))
```

因為兩個list，只有5是一樣的，這時候會就印出：
```
[1, 2, 3, 4, 6, 7, 8, 9]
```

如果改把list2改成：
```
list2 = [1,2,3,4]
```
那麼就會印出：`[5]`，因為只有5，是不一樣的。


---

善用`set().symmetric_difference()`，就可以很容易的找到兩個資料夾不同的地方啦！！



**如果這篇文章有幫助到你，歡迎在下方disqus留言版點擊愛心推荐哦！有任何問題請留言討論！**
**也歡迎把大魔術熊貓工程師的文章連結分享出去哦！！**