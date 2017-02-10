Go编程提供了一个非常简单的错误处理框架，以及内置的错误接口类型，如下声明：

    type error interface {
       Error() string
    }

函数通常返回错误作为最后一个返回值。 可使用`errors.New`来构造一个基本的错误消息，如下所示：

    func Sqrt(value float64)(float64, error) {
       if(value < 0){
          return 0, errors.New("Math: negative number passed to Sqrt")
       }
       return math.Sqrt(value)
    }

使用返回值和错误消息，如下所示 -

    result, err:= Sqrt(-1)

    if err != nil {
       fmt.Println(err)
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>示例

    package main

    import "errors"
    import "fmt"
    import "math"

    func Sqrt(value float64)(float64, error) {
       if(value < 0){
          return 0, errors.New("Math: negative number passed to Sqrt")
       }
       return math.Sqrt(value), nil
    }

    func main() {
       result, err:= Sqrt(-1)

       if err != nil {
          fmt.Println(err)
       }else {
          fmt.Println(result)
       }

       result, err = Sqrt(9)

       if err != nil {
          fmt.Println(err)
       }else {
          fmt.Println(result)
       }
    }

当上述代码编译和执行时，它产生以下结果：

    Math: negative number passed to Sqrt
    3

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言错误处理](##)


