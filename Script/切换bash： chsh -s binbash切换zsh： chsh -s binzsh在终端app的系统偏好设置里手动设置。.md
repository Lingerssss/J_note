- 切换bash： `chsh -s /bin/bash`
- 切换zsh： `chsh -s /bin/zsh`
- 在终端app的系统偏好设置里手动设置。

```shell
!/bin/bash
```





### 拼接字符串

```shell
your_name="runoob"
# 使用双引号拼接
greeting="hello, "$your_name" !"
greeting_1="hello, ${your_name} !"
echo $greeting  $greeting_1
# 使用单引号拼接
greeting_2='hello, '$your_name' !'
greeting_3='hello, ${your_name} !'
echo $greeting_2  $greeting_3
```



输出结果为：

```
hello, runoob ! hello, runoob !
```

实际结果并不像菜鸟教程中说的那样，单引号中也可以使用变量