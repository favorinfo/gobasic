Go编程语言提供了一个称为数组的数据结构，它可以存储相同类型的元素的固定大小顺序集合。 数组用于存储数据集合，但将数组视为同一类型的变量的集合通常更有用。

您可以声明一个数组变量，如`number`，并使用`number[0]`，`number[1]`和…，`number[99]`代替声明单个变量，如代替声明`number0`，`number1`，…和`number99`这样的单个变量。 数组中的特定元素是由指定索引来访问的。
所有数组由连续的内存位置组成。 最低地址对应于第一个元素，最高地址对应于最后一个元素。

![](http://www.yiibai.com/uploads/images/201702/0202/216160251_61179.jpg)

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>声明数组
----------------------------------------------------------------------------------------------------

要在Go中声明一个数组，程序员需要指定元素的类型和数组所需的元素数量如下：

    var variable_name [SIZE] variable_type

上面代码中定义的数组称为一维数组。**SIZE**必须是大于零的整数常量，类型可以是任何有效的Go数据类型。 例如，要声明一个名称为`balance`，它的类型为`float32`，并包含有 `10` 元素数组，请使用以下语句：

    var balance [10] float32

现在`balance`是一个变量数组，它可最多容纳`10`个浮点数。

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>初始化数组
------------------------------------------------------------------------------------------------------

可以在`Go`中逐一初始化数组，也可以使用单个语句一次性初始化，如下：

    var balance = [5]float32{1000.0, 2.0, 3.4, 7.0, 50.0}

大括号`{}`中的值的数量不能大于在方括号`[]`中为数组声明指定的元素数量。

如果省略数组的大小，则只创建一个足够容纳初始化的数组。 因此，可以使用如下写法：

    var balance = []float32{1000.0, 2.0, 3.4, 7.0, 50.0}

创建与上一个示例中完全相同的数组。以下是分配数组中单个元素的示例：

    balance[4] = 50.0

上面的语句将数组中编号为第`5`的元素赋值为`50.0`。所有数组以`0`作为它们的第一个元素的索引，也称为基本索引，数组的最后一个索引是数组的总大小减去`1`。下面图解是上面讨论的同一个数组的图形表示：

![](http://www.yiibai.com/uploads/images/201702/0202/407170201_13975.jpg)

> 注： 最后一个元素的索引数是 `4` (也就是`5`减去`1`)，而不是`5`。

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>访问数组元素
--------------------------------------------------------------------------------------------------------

通过索引数组名称来访问元素。这是通过将元素的索引放在数组名称后的方括号内。 例如访问第10个元素的值：

    float32 salary = balance[9]

上面的语句将从数组中获取第`10`个元素的值，并将其值赋给`salary`变量。下面是一个使用所有上述三个概念的例子。 声明，赋值和访问数组：

    package main

    import "fmt"

    func main() {
       var n [10]int /* n is an array of 10 integers */
       var i,j int

       /* initialize elements of array n to 0 */         
       for i = 0; i < 10; i++ {
          n[i] = i + 100 /* set element at location i to i + 100 */
       }

       /* output each array element's value */
       for j = 0; j < 10; j++ {
          fmt.Printf("Element[%d] = %d\n", j, n[j] )
       }
    }

当上述代码编译和执行时，它产生以下结果：

    Element[0] = 100
    Element[1] = 101
    Element[2] = 102
    Element[3] = 103
    Element[4] = 104
    Element[5] = 105
    Element[6] = 106
    Element[7] = 107
    Element[8] = 108
    Element[9] = 109

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>Go语言中数组的详细信息
------------------------------------------------------------------------------------------------------------------

数组在Go语言中很重要，应该需要了解更多的信息。以下几个与数组相关的重要概念应该向Go程序员明确：

| 概念                                                                                                | 描述                                                             |
|-----------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| [多维数组](http://www.yiibai.com/go/go_multi_dimensional_arrays.html "多维数组")                    | Go支持多维数组，多维数组的最简单的形式是二维数组。               |
| [将数组传递给函数](http://www.yiibai.com/go/go_passing_arrays_to_functions.html "将数组传递给函数") | 可以通过指定数组的名称而不使用索引，将指向数组的指针传递给函数。 |

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言数组](##)


