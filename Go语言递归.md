递归是以自相似的方式重复项的过程。这同样适用于其它编程语言，在编程语言中允许在函数内调用同一个函数称为递归调用，如下所示。

    func recursion() {
       recursion() /* function calls itself */
    }

    func main() {
       recursion()
    }

Go编程语言支持递归，即函数调用自身的函数。 但是在使用递归时，程序员需要注意在函数中定义或设置一个退出条件，否则它会进入无限循环。

递归函数非常有用，可用于解决许多数学问题，如计算数字的阶乘，生成斐波那契数列等。

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>数字阶乘示例

下面是一个例子，它使用递归函数来计算给定数字的阶乘：

    package main

    import "fmt"

    func factorial(i int)int {
       if(i <= 1) {
          return 1
       }
       return i * factorial(i - 1)
    }

    func main() { 
       var i int = 15
       fmt.Printf("Factorial of %d is %d", i, factorial(i))
    }

当上述代码编译和执行时，它产生以下结果：

    Factorial of 15 is 2004310016

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>斐波那契系列示例

下面是另一个例子，它使用递归函数按给定数字生成斐波那契数列：

    package main

    import "fmt"

    func fibonaci(i int) (ret int) {
       if i == 0 {
          return 0
       }

       if i == 1 {
          return 1
       }

       return fibonaci(i-1) + fibonaci(i-2)
    }

    func main() {
       var i int
       for i = 0; i < 10; i++ {
          fmt.Printf("%d ", fibonaci(i))
       }
    }

当上述代码编译和执行时，它产生以下结果：

    0 1 1 2 3 5 8 13 21 34

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言递归](##)


