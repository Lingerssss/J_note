```
 - 分别写一个 asp.net webapi2, asp.net mvc, asp.net core的example，http://url?param=ping
    - 三个asp.net区别
    - POST api, json如何被转化成为POCO的，各种基本类型, Datetime, Enum, int, string
    - How to add Exception Log?
```



```c#
1     public String GetResultByParameter(String parameter)
2     {
4       if (parameter.Equals("ping"))
5       {
6        return "pong"
7       }
8       throw new HttpResponseException(HttpStatusCode.NotFound);
9     }
```

Asp.net mvc主要用来基于mvc模式开发网页，Asp.net webapi主要用来开发restful风格的接口。但两者没有本质区别，asp.net mvc完全可以自己实现一套restful webapi。asp.net core发布之后这两者已经合并了。



![image-20211217120314821](https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20211217120314821.png)



![image-20211217102343076](https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20211217102343076.png)

Yarn watch