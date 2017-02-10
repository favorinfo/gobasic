在学习Go语言编程之前，我们需要安装和配置好Go语言的开发环境。可以选择线上的编译器：<http://tour.golang.org/welcome/1> 来直接执行代码。也可以在您自己的计算机上安装开发编译环境。

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>本地环境设置
--------------------------------------------------------------------------------------------------------

如果您愿意在本地环境安装和配置Go编程语言，则需要在计算机上提供以下两个软件：

-   文本编辑器
-   Go编译器

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>文本编辑器
------------------------------------------------------------------------------------------------------

这是用于编写您的程序代码。常见的几个编辑器包括Windows记事本，OS编辑命令，`Brief`，`Epsilon`，`EMACS`和`vim`(或`vi`)。

文本编辑器的名称和版本可能因不同的操作系统而异。例如，记事本只能在Windows上使用，vim(或vi)可以在Windows以及Linux或UNIX上使用。

使用编辑器创建的文件称为源文件，源文件中包含程序的源代码。Go程序的源文件通常使用扩展名“`.go`”来命名。

在开始编程之前，确保您安装好并熟练使用一个文本编辑器，并且有足够的经验来编写计算机程序代码，将代码保存在文件中，编译并最终执行它。

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>Go编译器
----------------------------------------------------------------------------------------------------

在源文件中编写的源代码是人类可读的源程序。 它需要“编译”变成机器语言，以便CPU可以根据给出的指令实际执行程序。

这个Go编程语言编译器用于将源代码编译成可执行程序。这里假设您知道或了解编程语言编译器的基本知识。

Go发行版本是FreeBSD(版本8及更高版本)，Linux，Mac OS X(Snow Leopard及更高版本)和具有`32`位(386)和`64`位(amd64)x86处理器架构的Windows操作系统的二进制安装版本 。

以下部分将演示如何在各种操作系统上安装**Go语言**环境的二进制分发包。

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>下载Go存档文件
----------------------------------------------------------------------------------------------------------

从链接【[Go下载](http://golang.org/dl/ "Go下载")】中下载最新版本的Go可安装的归档文件。在写本教程的时候，选择的是`go1.7.4.windows-amd64.msi`并将下载到桌面上。

> 注：写本教程的时，使用的电脑是：Windows 10 64bit 系统

如果操作系统不一样，可选择对应版本下载安装。

| 操作系统 | 存档名称                   |
|----------|----------------------------|
| Windows  | go1.7.windows-amd64.msi    |
| Linux    | go1.7.linux-amd64.tar.gz   |
| Mac      | go1.7.4.darwin-amd64.pkg   |
| FreeBSD  | go1.7.freebsd-amd64.tar.gz |

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>在UNIX/Linux/Mac OS X和FreeBSD上安装
--------------------------------------------------------------------------------------------------------------------------------

将下载归档文件解压缩到`/usr/local`目录中，在`/usr/local/go`目录创建一个Go树。 例如：

    tar -C /usr/local -xzf go1.7.4.linux-amd64.tar.gz

将`/usr/local/go/bin`添加到`PATH`环境变量。

| 操作系统 | 输出                                |
|----------|-------------------------------------|
| Linux    | export PATH=$PATH:/usr/local/go/bin |
| Mac      | export PATH=$PATH:/usr/local/go/bin |
| FreeBSD  | export PATH=$PATH:/usr/local/go/bin |

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>在Windows上安装
-----------------------------------------------------------------------------------------------------------

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

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言开发环境安装配置](##)


