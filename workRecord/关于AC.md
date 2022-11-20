:thinking_face:有一个疑问想问一下。我们卡片的AC是不是有些混乱，感觉大家都有点各显神通:fast_parrot:。我觉得这里面有一个原因是我们的AC都是dev自己写的，相当于我给我自己做的事情定标准。一人兼任了运动员和裁判员:smiling_imp:。

我的主要问题是AC需要具体到什么层级呢？
目前我们的AC主要关注两个方面：
1是checkmarx的检测需要修复
2是不影响已有的业务功能

实际上我们的AC可能是这样的（我拼凑的，大家不需要去对应）：
1.Restsharp升级到2.0.0版本
2.Make sure existing test cases pass

```
AC: upgrade restsharp to 1.0

Solution: upgrade restsharp to 1.0

How to test: already upgrade?
```



这就产生了更多的问题，比如升级版本可能是属于solition，比如pipeline通过是一条默认的ac。

我觉得这些和我们项目的特殊性相关。
这是我对

Description：

- 问题本身是什么 
- 问题影响的scope是什么。 

Solution: 

- 解决问题的方法，eg: Upgrade, remove, escape

How to test: 

对应AC的两部分

- checkmarx中相应的codebase没有问题，

- 具体的业务场景功能正常



总的来说我觉得写卡片和写代码是一样的。还是需要让别人比较容易看懂的。为了这个目的，是不是统一风格比较好呢？

