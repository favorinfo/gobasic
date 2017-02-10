可能有这样的一种情况，当需要执行一段代码多次。一般来说，语句是按顺序执行的，例如,函数中的第一个语句首先执行，然后是第二个语句，第三个语句…，依此类推。

编程语言中都有提供允许更复杂的执行路径的各种控制结构。

循环语句允许我们多次执行一个语句或一组语句，以下是大多数编程语言中循环语句的一般形式：

![](http://www.yiibai.com/uploads/images/201702/0102/613190248_90185.jpg)

Go编程语言提供以下几种类型的循环来处理循环。单击以下链接以了解其详细信息。

| 循环类型                                                             | 描述                                         |
|----------------------------------------------------------------------|----------------------------------------------|
| [for循环](http://www.yiibai.com/go/go_for_loop.html "for循环")       | 多次执行语句序列，并缩写代码管理循环的变量。 |
| [嵌套循环](http://www.yiibai.com/go/go_nested_loops.html "嵌套循环") | 可以在`for`循环中使用一个或多个`for`循环。   |

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>循环控制语句

循环控制语句改变循环正常执行序列。当执行离开作用域时，在循环作用域中创建的所有自动对象都将被销毁。

Go支持以下控制语句。单击以下链接以了解其详细信息。

| 控制语句                                                                           | 描述                                                                       |
|------------------------------------------------------------------------------------|----------------------------------------------------------------------------|
| [break语句](http://www.yiibai.com/go/go_break_statement.html "break语句")          | 终止`for`循环或`switch`语句，并将执行转移到`for`循环或`switch`之后的语句。 |
| [continue语句](http://www.yiibai.com/go/go_continue_statement.html "continue语句") | 循环跳过其主体的其余部分，并立即重新测试其状态。                           |
| [goto语句](http://www.yiibai.com/go/go_goto_statement.html "goto语句")             | 将控制转移到带标签的语句。                                                 |

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>无限循环

如果条件永远不为假，则循环变为无限循环。 `for`循环传统上用于此目的。 因为形成`for`循环的三个表达式都不是必需的，所以可以通过将条件表达式留空或将`true`传递给它来进行无限循环。

    package main

    import "fmt"

    func main() {
       for true  {
           fmt.Printf("This loop will run forever.\n");
       }
    }

当条件表达式不存在时，假定为真。可能有一个初始化和增量表达式，但是Go程序员更常使用`for(;;)`结构来表示一个无限循环。

> 注意：可以通过按`Ctrl + C`键终止无限循环。

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言循环](##)


