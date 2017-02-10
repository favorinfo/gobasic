类型转换是一种将变量从一种数据类型转换为另一种数据类型的方法。 例如，如果要将长整型值存储到简单整数类型，那么可以将转换`long`类型为`int`类型。可以使用**转换操作符**将值从一种类型转换为另一种类型，如下所示：

    type_name(expression)

看看下面的例子，其中转换操作符将一个整数变量除以另一个整数变量并将其结果值转换为浮点数。

    package main

    import "fmt"

    func main() {
       var sum int = 17
       var count int = 5
       var mean float32

       mean = float32(sum)/float32(count)
       fmt.Printf("Value of mean : %f\n",mean)
    }

当上述代码编译和执行时，它产生以下结果：

    Value of mean : 3.400000

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言类型转换](##)


