在学习Go语言编程之前，我们需要安装和配置好Go语言的开发环境。可以选择线上的编译器：<http://tour.golang.org/welcome/1> 来直接执行代码。也可以在您自己的计算机上安装开发编译环境。

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>Go本地环境设置
----------------------------------------------------------------------------------------------------------

如果您愿意在本地环境安装和配置Go编程语言，则需要在计算机上提供以下两个软件：

-   文本编辑器
-   Go编译器

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>文本编辑器

这是用于编写您的程序代码。常见的几个编辑器包括Windows记事本，OS编辑命令，`Brief`，`Epsilon`，`EMACS`和`vim`(或`vi`)。

文本编辑器的名称和版本可能因不同的操作系统而异。例如，记事本只能在Windows上使用，vim(或vi)可以在Windows以及Linux或UNIX上使用。

使用编辑器创建的文件称为源文件，源文件中包含程序的源代码。Go程序的源文件通常使用扩展名“`.go`”来命名。

在开始编程之前，确保您安装好并熟练使用一个文本编辑器，并且有足够的经验来编写计算机程序代码，将代码保存在文件中，编译并最终执行它。

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>Go编译器

在源文件中编写的源代码是人类可读的源程序。 它需要“编译”变成机器语言，以便CPU可以根据给出的指令实际执行程序。

这个Go编程语言编译器用于将源代码编译成可执行程序。这里假设您知道或了解编程语言编译器的基本知识。

Go发行版本是FreeBSD(版本8及更高版本)，Linux，Mac OS X(Snow Leopard及更高版本)和具有`32`位(386)和`64`位(amd64)x86处理器架构的Windows操作系统的二进制安装版本 。

以下部分将演示如何在各种操作系统上安装**Go语言**环境的二进制分发包。

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>下载Go存档文件

从链接【[Go下载](http://golang.org/dl/ "Go下载")】中下载最新版本的Go可安装的归档文件。在写本教程的时候，选择的是`go1.7.4.windows-amd64.msi`并将下载到桌面上。

> 注：写本教程的时，使用的电脑是：Windows 10 64bit 系统

如果操作系统不一样，可选择对应版本下载安装。

| 操作系统 | 存档名称                   |
|----------|----------------------------|
| Windows  | go1.7.windows-amd64.msi    |
| Linux    | go1.7.linux-amd64.tar.gz   |
| Mac      | go1.7.4.darwin-amd64.pkg   |
| FreeBSD  | go1.7.freebsd-amd64.tar.gz |

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>在UNIX/Linux/Mac OS X和FreeBSD上安装

将下载归档文件解压缩到`/usr/local`目录中，在`/usr/local/go`目录创建一个Go树。 例如：

    tar -C /usr/local -xzf go1.7.4.linux-amd64.tar.gz

将`/usr/local/go/bin`添加到`PATH`环境变量。

| 操作系统 | 输出                                |
|----------|-------------------------------------|
| Linux    | export PATH=$PATH:/usr/local/go/bin |
| Mac      | export PATH=$PATH:/usr/local/go/bin |
| FreeBSD  | export PATH=$PATH:/usr/local/go/bin |

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>在Windows上安装

使用MSI文件并按照提示安装Go工具。 默认情况下，安装程序使用`C:\Go`目录。安装程序应该在窗口的PATH环境变量中设置`C:\Go\bin`目录。重新启动后，打开的命令提示验证更改是否生效。

**验证安装结果**

在`F:\worksp\golang`中创建一个`test.go`的go文件。编写并保存以下代码到 `test.go` 文件中。

    package main

    import "fmt"

    func main() {
       fmt.Println("Hello, World!")
    }

现在运行`test.go`查看结果并验证输出结果如下：

    F:\worksp\golang>go run test.go
    Hello, World!

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>包的使用
----------------------------------------------------------------------------------------------------

每个 Go 程序都是由包组成的。
程序运行的入口是包 `main` 。
这个程序使用并导入了包 “`fmt`“ 和 “`math/rand`“ 。
按照惯例，包名与导入路径的最后一个目录一致。例如，”`math/rand`“ 包由 `package rand` 语句开始。

> 注意：这个程序的运行环境是确定性的，因此 rand.Intn 每次都会返回相同的数字。

    package main

    import (
        "fmt"
        "math/rand"
    )

    func main() {
        fmt.Println("My favorite number is", rand.Intn(10))
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>导入包

这个代码用圆括号组合了导入，这是“打包”导入语句。

同样可以编写多个导入语句，例如：

    import "fmt"
    import "math"

不过使用打包的导入语句是更好的形式。

    package main

    import (
        "fmt"
        "math"
    )

    func main() {
        fmt.Printf("Now you have %g problems.", math.Sqrt(7))
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>导出名称

在 `Go` 中，首字母大写的名称是被导出的。

在导入包之后，只能访问包所导出的名字，任何未导出的名字是不能被包外的代码访问的。

`Foo` 和 `FOO` 都是被导出的名称。名称 `foo` 是不会被导出的。

执行代码，注意编译器报的错误。

然后将 `math.pi` 改名为 `math.Pi` 再试着执行一下。

    package main

    import (
        "fmt"
        "math"
    )

    func main() {
        fmt.Println(math.pi)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>函数

函数可以没有参数或接受多个参数。
在这个例子中， `add` 接受两个 `int` 类型的参数。
注意类型在变量名之后 。

    package main

    import "fmt"

    func add(x int, y int) int {
        return x + y
    }

    func main() {
        fmt.Println(add(42, 13))
    }

当两个或多个连续的函数命名参数是同一类型，则除了最后一个类型之外，其他都可以省略。

在这个例子中 ，

    x int, y int

可缩写为：

    x, y int

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>函数多值返回

函数可以返回任意数量的返回值。
`swap` 函数返回了两个字符串。

    package main

    import "fmt"

    func swap(x, y string) (string, string) {
        return y, x
    }

    func main() {
        a, b := swap("hello", "world")
        fmt.Println(a, b)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>函数中命名返回值

Go 的返回值可以被命名，并且就像在函数体开头声明的变量那样使用。
返回值的名称应当具有一定的意义，可以作为文档使用。
没有参数的 `return` 语句返回各个返回变量的当前值。这种用法被称作“裸”返回。
直接返回语句仅应当用在像下面这样的短函数中。在长的函数中它们会影响代码的可读性。

    package main

    import "fmt"

    func split(sum int) (x, y int) {
        x = sum * 4 / 9
        y = sum - x
        return
    }

    func main() {
        fmt.Println(split(17))
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>变量

`var` 语句定义了一个变量的列表；跟函数的参数列表一样，类型在后面。就像在这个例子中看到的一样， `var` 语句可以定义在包或函数级别。

    package main

    import "fmt"

    var c, python, java bool

    func main() {
        var i int
        fmt.Println(i, c, python, java)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>初始化变量

变量定义可以包含初始值，每个变量对应一个。如果初始化是使用表达式，则可以省略类型；变量从初始值中获得类型。

    package main

    import "fmt"

    var i, j int = 1, 2

    func main() {
        var c, python, java = true, false, "no!"
        fmt.Println(i, j, c, python, java)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>短声明变量

在函数中， `:=` 简洁赋值语句在明确类型的地方，可以用于替代 `var` 定义。
函数外的每个语句都必须以关键字开始( `var` 、 `func` 、等等)， `:=`结构不能使用在函数外。

    package main

    import "fmt"

    func main() {
        var i, j int = 1, 2
        k := 3
        c, python, java := true, false, "no!"

        fmt.Println(i, j, k, c, python, java)
    }

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>基本数据类型
--------------------------------------------------------------------------------------------------------

Go 的基本类型有：

    bool

    string

    int  int8  int16  int32  int64
    uint uint8 uint16 uint32 uint64 uintptr

    byte // uint8 的别名

    rune // int32 的别名
         // 代表一个Unicode码

    float32 float64

    complex64 complex128

这个例子演示了具有不同类型的变量。 同时与导入语句一样，变量的定义“打包”在一个语法块中。

`int`，`uint` 和 `uintptr` 类型在32位的系统上一般是32位，而在64位系统上是64位。当你需要使用一个整数类型时，应该首选 `int`，仅当有特别的理由才使用定长整数类型或者无符号整数类型。

    package main

    import (
        "fmt"
        "math/cmplx"
    )

    var (
        ToBe   bool       = false
        MaxInt uint64     = 1<<64 - 1
        z      complex128 = cmplx.Sqrt(-5 + 12i)
    )

    func main() {
        const f = "%T(%v)\n"
        fmt.Printf(f, ToBe, ToBe)
        fmt.Printf(f, MaxInt, MaxInt)
        fmt.Printf(f, z, z)
    }

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>零值
------------------------------------------------------------------------------------------------

变量在定义时没有明确的初始化时会赋值为 零值 。

零值是：

数值类型为 `0` ，
布尔类型为 `false` ，
字符串为 “” (空字符串)。

    package main

    import "fmt"

    func main() {
        var i int
        var f float64
        var b bool
        var s string
        fmt.Printf("%v %v %v %q\n", i, f, b, s)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>类型转换

表达式`T(v)` 将值 `v` 转换为类型 `T` 。

一些关于数值的转换：

    var i int = 42
    var f float64 = float64(i)
    var u uint = uint(f)

或者，更加简单的形式：

    i := 42
    f := float64(i)
    u := uint(f)

与 C 不同的是 Go 的在不同类型之间的项目赋值时需要显式转换。 试着移除例子中 `float64` 或 `int` 的转换看看会发生什么。

    package main

    import (
        "fmt"
        "math"
    )

    func main() {
        var x, y int = 3, 4
        var f float64 = math.Sqrt(float64(x*x + y*y))
        var z uint = uint(f)
        fmt.Println(x, y, z)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>类型推导

类型推导
在定义一个变量却并不显式指定其类型时(使用 `:=` 语法或者 `var =`表达式语法)， 变量的类型由(等号)右侧的值推导得出。

当右值定义了类型时，新变量的类型与其相同：

    var i int
    j := i // j 也是一个 int

但是当右边包含了未指名类型的数字常量时，新的变量就可能是 `int` 、 `float64` 或 `complex128` 。 这取决于常量的精度：

    i := 42           // int
    f := 3.142        // float64
    g := 0.867 + 0.5i // complex128

尝试修改演示代码中 `v` 的初始值，并观察这是如何影响其类型的。

    package main

    import "fmt"

    func main() {
        v := 42 // change me!
        fmt.Printf("v is of type %T\n", v)
    }

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>常量
------------------------------------------------------------------------------------------------

常量的定义与变量类似，只不过使用 `const` 关键字。

常量可以是字符、字符串、布尔或数字类型的值。

常量不能使用 `:=` 语法定义。

    package main

    import "fmt"

    const Pi = 3.14

    func main() {
        const World = "世界"
        fmt.Println("Hello", World)
        fmt.Println("Happy", Pi, "Day")

        const Truth = true
        fmt.Println("Go rules?", Truth)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>数值常量

数值常量是高精度的值 。
一个未指定类型的常量由上下文来决定其类型。
也尝试一下输出 `needInt(Big)` 吧。
(`int` 可以存放最大`64`位的整数，根据平台不同有时会更少。)

    package main

    import "fmt"

    const (
        Big   = 1 << 100
        Small = Big >> 99
    )

    func needInt(x int) int { return x*10 + 1 }
    func needFloat(x float64) float64 {
        return x * 0.1
    }

    func main() {
        fmt.Println(needInt(Small))
        fmt.Println(needFloat(Small))
        fmt.Println(needFloat(Big))
    }

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>控制流
--------------------------------------------------------------------------------------------------

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>for

Go 只有一种循环结构 —— `for` 循环。

基本的 `for` 循环包含三个由分号分开的组成部分：

初始化语句：在第一次循环执行前被执行
循环条件表达式：每轮迭代开始前被求值
后置语句：每轮迭代后被执行
初始化语句一般是一个短变量声明，这里声明的变量仅在整个 `for` 循环语句可见。

如果条件表达式的值变为 `false`，那么迭代将终止。

注意：不像 C，Java，或者 Javascript 等其他语言，`for` 语句的三个组成部分 并不需要用括号括起来，但循环体必须用`{ }`括起来。

    package main

    import "fmt"

    func main() {
        sum := 0
        for i := 0; i < 10; i++ {
            sum += i
        }
        fmt.Println(sum)
    }

循环初始化语句和后置语句都是可选的，如下示例代码所示 -

    package main

    import "fmt"

    func main() {
        sum := 1
        for ; sum < 1000; {
            sum += sum
        }
        fmt.Println(sum)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>for 是 Go 的 “while”

基于此可以省略分号：C 的 `while` 在 Go 中叫做 `for` 。

    package main

    import "fmt"

    func main() {
        sum := 1
        for sum < 1000 {
            sum += sum
        }
        fmt.Println(sum)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>死循环

如果省略了循环条件，循环就不会结束，因此可以用更简洁地形式表达死循环。

    package main

    func main() {
        for {// 无退出条件，变成死循环
        }
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>if

就像 `for` 循环一样，Go 的 `if` 语句也不要求用`( )` 将条件括起来，同时，`{ }`还是必须有的。

    package main

    import (
        "fmt"
        "math"
    )

    func sqrt(x float64) string {
        if x < 0 {
            return sqrt(-x) + "i"
        }
        return fmt.Sprint(math.Sqrt(x))
    }

    func main() {
        fmt.Println(sqrt(2), sqrt(-4))
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>if 的便捷语句

跟 `for` 语句一样， `if` 语句可以在条件之前执行一个简单语句。
由这个语句定义的变量的作用域仅在 `if` 范围之内。
(在最后的 `return` 语句处使用 `v` 看看。)

    package main

    import (
        "fmt"
        "math"
    )

    func pow(x, n, lim float64) float64 {
        if v := math.Pow(x, n); v < lim {
            return v
        }
        return lim
    }

    func main() {
        fmt.Println(
            pow(3, 2, 10),
            pow(3, 3, 20),
        )
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>if 和 else

在 `if` 的便捷语句定义的变量同样可以在任何对应的 `else` 块中使用。
(提示：两个 `pow` 调用都在 `main` 调用 `fmt.Println` 前执行完毕了。)

    package main

    import (
        "fmt"
        "math"
    )

    func pow(x, n, lim float64) float64 {
        if v := math.Pow(x, n); v < lim {
            return v
        } else {
            fmt.Printf("%g >= %g\n", v, lim)
        }
        // 这里开始就不能使用 v 了
        return lim
    }

    func main() {
        fmt.Println(
            pow(3, 2, 10),
            pow(3, 3, 20),
        )
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>switch语句

你可能已经知道 `switch` 语句会长什么样了。
除非以 `fallthrough` 语句结束，否则分支会自动终止。

    package main

    import (
        "fmt"
        "runtime"
    )

    func main() {
        fmt.Print("Go runs on ")
        switch os := runtime.GOOS; os {
        case "darwin":
            fmt.Println("OS X.")
        case "linux":
            fmt.Println("Linux.")
        default:
            // freebsd, openbsd,
            // plan9, windows...
            fmt.Printf("%s.", os)
        }
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>switch 的执行顺序

`switch` 的条件从上到下的执行，当匹配成功的时候停止。

(例如，

    switch i {
    case 0:
    case f():
    }

当 `i==0` 时不会调用 `f` 。)

注意：Go playground 中的时间总是从 `2009-11-10 23:00:00 UTC` 开始， 如何校验这个值作为一个练习留给读者完成。

    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        fmt.Println("When's Saturday?")
        today := time.Now().Weekday()
        switch time.Saturday {
        case today + 0:
            fmt.Println("Today.")
        case today + 1:
            fmt.Println("Tomorrow.")
        case today + 2:
            fmt.Println("In two days.")
        default:
            fmt.Println("Too far away.")
        }
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>没有条件的 switch

没有条件的 `switch` 同 `switch true` 一样。
这一构造使得可以用更清晰的形式来编写长的 `if-then-else` 链。

    package main

    import (
        "fmt"
        "time"
    )

    func main() {
        t := time.Now()
        switch {
        case t.Hour() < 12:
            fmt.Println("Good morning!")
        case t.Hour() < 17:
            fmt.Println("Good afternoon.")
        default:
            fmt.Println("Good evening.")
        }
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>defer语句

`defer` 语句会延迟函数的执行直到上层函数返回。
延迟调用的参数会立刻生成，但是在上层函数返回前函数都不会被调用。

    package main

    import "fmt"

    func main() {
        defer fmt.Println("world")

        fmt.Println("hello")
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>defer 栈

延迟的函数调用被压入一个栈中。当函数返回时， 会按照后进先出的顺序调用被延迟的函数调用。

    package main

    import "fmt"

    func main() {
        fmt.Println("counting")

        for i := 0; i < 10; i++ {
            defer fmt.Println(i)
        }

        fmt.Println("done")
    }

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>指针
------------------------------------------------------------------------------------------------

Go 具有指针。 指针保存了变量的内存地址。

类型 `*T` 是指向类型 `T`的值的指针。其零值是 `nil` 。

    var p *int

`&` 符号会生成一个指向其作用对象的指针。

    i := 42
    p = &i

`*`符号表示指针指向的底层的值。

    fmt.Println(*p) // 通过指针 p 读取 i
    *p = 21         // 通过指针 p 设置 i

这也就是通常所说的“间接引用”或“非直接引用”。
与 C 不同，Go 没有指针运算。

    package main

    import "fmt"

    func main() {
        i, j := 42, 2701

        p := &i         // point to i
        fmt.Println(*p) // read i through the pointer
        *p = 21         // set i through the pointer
        fmt.Println(i)  // see the new value of i

        p = &j         // point to j
        *p = *p / 37   // divide j through the pointer
        fmt.Println(j) // see the new value of j
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>结构体

一个结构体( `struct` )就是一个字段的集合。(而 type 的含义跟其字面意思相符。)

    package main

    import "fmt"

    type Vertex struct {
        X int
        Y int
    }

    func main() {
        fmt.Println(Vertex{1, 2})
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>结构体字段

结构体字段使用点号来访问。

    package main

    import "fmt"

    type Vertex struct {
        X int
        Y int
    }

    func main() {
        v := Vertex{1, 2}
        v.X = 4
        fmt.Println(v.X)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>结构体指针

结构体字段可以通过结构体指针来访问。
通过指针间接的访问是透明的。

    package main

    import "fmt"

    type Vertex struct {
        X int
        Y int
    }

    func main() {
        v := Vertex{1, 2}
        p := &v
        p.X = 1e9
        fmt.Println(v)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>结构体符文

结构体符文表示通过结构体字段的值作为列表来新分配一个结构体。
使用 `Name:` 语法可以仅列出部分字段。(字段名的顺序无关。)
特殊的前缀 `&` 返回一个指向结构体的指针。

    package main

    import "fmt"

    type Vertex struct {
        X, Y int
    }

    var (
        v1 = Vertex{1, 2}  // 类型为 Vertex
        v2 = Vertex{X: 1}  // Y:0 被省略
        v3 = Vertex{}      // X:0 和 Y:0
        p  = &Vertex{1, 2} // 类型为 *Vertex
    )

    func main() {
        fmt.Println(v1, p, v2, v3)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>数组

类型 `[n]T` 是一个有 `n` 个类型为 `T` 的值的数组。

表达式

    var a [10]int

定义变量 `a` 是一个有十个整数的数组。

数组的长度是其类型的一部分，因此数组不能改变大小。这看起来是一个制约，但是请不要担心； Go 提供了更加便利的方式来使用数组。

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>切片(slice)

一个 `slice` 会指向一个序列的值，并且包含了长度信息。

`[]T` 是一个元素类型为 `T` 的 切片(`slice`)。

`len(s)`返回 `slice s`的长度。

    package main

    import "fmt"

    func main() {
        s := []int{2, 3, 5, 7, 11, 13}
        fmt.Println("s ==", s)

        for i := 0; i < len(s); i++ {
            fmt.Printf("s[%d] == %d\n", i, s[i])
        }
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>切片(slice)的切片

切片(slice)可以包含任意的类型，包括另一个 `slice`。

    package main

    import (
        "fmt"
        "strings"
    )

    func main() {
        // Create a tic-tac-toe board.
        game := [][]string{
            []string{"_", "_", "_"},
            []string{"_", "_", "_"},
            []string{"_", "_", "_"},
        }

        // The players take turns.
        game[0][0] = "X"
        game[2][2] = "O"
        game[2][0] = "X"
        game[1][0] = "O"
        game[0][2] = "X"

        printBoard(game)
    }

    func printBoard(s [][]string) {
        for i := 0; i < len(s); i++ {
            fmt.Printf("%s\n", strings.Join(s[i], " "))
        }
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>对 slice 切片

`slice` 可以重新切片，创建一个新的 `slice` 值指向相同的数组。

表达式

    s[lo:hi]

表示从 `lo` 到 `hi-1` 的 `slice` 元素，含前端，不包含后端。因此

    s[lo:lo]

是空的，而

    s[lo:lo+1]

有一个元素。

    package main

    import "fmt"

    func main() {
        s := []int{2, 3, 5, 7, 11, 13}
        fmt.Println("s ==", s)
        fmt.Println("s[1:4] ==", s[1:4])

        // 省略下标代表从 0 开始
        fmt.Println("s[:3] ==", s[:3])

        // 省略上标代表到 len(s) 结束
        fmt.Println("s[4:] ==", s[4:])
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>构造 slice

`slice` 由函数 `make` 创建。这会分配一个全是零值的数组并且返回一个 `slice` 指向这个数组：

    a := make([]int, 5)  // len(a)=5

为了指定容量，可传递第三个参数到 `make`：

    b := make([]int, 0, 5) // len(b)=0, cap(b)=5

    b = b[:cap(b)] // len(b)=5, cap(b)=5
    b = b[1:]      // len(b)=4, cap(b)=4

参考以下示例代码 -

    package main

    import "fmt"

    func main() {
        a := make([]int, 5)
        printSlice("a", a)
        b := make([]int, 0, 5)
        printSlice("b", b)
        c := b[:2]
        printSlice("c", c)
        d := c[2:5]
        printSlice("d", d)
    }

    func printSlice(s string, x []int) {
        fmt.Printf("%s len=%d cap=%d %v\n",
            s, len(x), cap(x), x)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>nil slice

`slice` 的零值是 `nil` 。

一个 `nil` 的 `slice` 的长度和容量是 `0`。

    package main

    import "fmt"

    func main() {
        var z []int
        fmt.Println(z, len(z), cap(z))
        if z == nil {
            fmt.Println("nil!")
        }
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>向 slice 添加元素

向 `slice` 的末尾添加元素是一种常见的操作，因此 Go 提供了一个内建函数 `append` 。 内建函数的文档对 `append` 有详细介绍。

    func append(s []T, vs ...T) []T

`append` 的第一个参数 `s` 是一个元素类型为 `T` 的 `slice` ，其余类型为 `T` 的值将会附加到该 `slice` 的末尾。

`append` 的结果是一个包含原 `slice` 所有元素加上新添加的元素的 `slice`。

如果 `s` 的底层数组太小，而不能容纳所有值时，会分配一个更大的数组。 返回的 `slice` 会指向这个新分配的数组。

    package main

    import "fmt"

    func main() {
        var a []int
        printSlice("a", a)

        // append works on nil slices.
        a = append(a, 0)
        printSlice("a", a)

        // the slice grows as needed.
        a = append(a, 1)
        printSlice("a", a)

        // we can add more than one element at a time.
        a = append(a, 2, 3, 4)
        printSlice("a", a)
    }

    func printSlice(s string, x []int) {
        fmt.Printf("%s len=%d cap=%d %v\n",
            s, len(x), cap(x), x)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>范围(range)

`for` 循环的 `range` 格式可以对 `slice` 或者 `map` 进行迭代循环。

当使用 `for` 循环遍历一个 `slice` 时，每次迭代 `range` 将返回两个值。 第一个是当前下标(序号)，第二个是该下标所对应元素的一个拷贝。

    package main

    import "fmt"

    var pow = []int{1, 2, 4, 8, 16, 32, 64, 128}

    func main() {
        for i, v := range pow {
            fmt.Printf("2**%d = %d\n", i, v)
        }
    }

可以通过赋值给 `_` 来忽略序号和值。

如果只需要索引值，去掉 “ , `value` ” 的部分即可。

    package main

    import "fmt"

    func main() {
        pow := make([]int, 10)
        for i := range pow {
            pow[i] = 1 << uint(i)
        }
        for _, value := range pow {
            fmt.Printf("%d\n", value)
        }
    }

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言入门](##)


