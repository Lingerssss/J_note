# c#

1

Bit就是位

byte字节

1字节=8位

1E3的数据类型

1.0肯定是double，1.0f才是float

可以用2的幂次方组合起来的数字才能精确表示。

非高精度需求用float即可



2

int转byte如果越界，先把int写成2进制，然后取高八位或低八位（根据语言决定）。

如0x1234,

二进制为0001 0010 0011 0100，取后八位00110100，等于52



3 int转float再转int精度丢失，不应使用



4 没有unchecked的话，0xfffffff0会显示越界

```c#
        public void should_do_complement_operation()
        {
            // change "default(int)" to correct value. You should use Hex representation.
            const int expectedResult = unchecked((int)0xfffffff0);
            Console.WriteLine(expectedResult);
            Assert.Equal(expectedResult, ~0xf);
        }
```

5. Byte\short等数据类型进行四则运算后的结果会被转为int，为了提醒用户运算结果可能会溢出
6. 在C#的浮点数计算中，0除以0将得到NaN，正数除以0将得到PositiveInfinity,负数除以0将得到NegativeInfinity。C#中浮点数运算从不引发异常





