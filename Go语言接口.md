Go编程提供了另一种称为接口(`interfaces`)的数据类型，它代表一组方法签名。`struct`数据类型实现这些接口以具有接口的方法签名的方法定义。

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>语法

    /* define an interface */
    type interface_name interface {
       method_name1 [return_type]
       method_name2 [return_type]
       method_name3 [return_type]
       ...
       method_namen [return_type]
    }

    /* define a struct */
    type struct_name struct {
       /* variables */
    }

    /* implement interface methods*/
    func (struct_name_variable struct_name) method_name1() [return_type] {
       /* method implementation */
    }
    ...
    func (struct_name_variable struct_name) method_namen() [return_type] {
       /* method implementation */
    }

### <a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>示例

    package main

    import (
       "fmt"
       "math"
    )

    /* define an interface */
    type Shape interface {
       area() float64
    }

    /* define a circle */
    type Circle struct {
       x,y,radius float64
    }

    /* define a rectangle */
    type Rectangle struct {
       width, height float64
    }

    /* define a method for circle (implementation of Shape.area())*/
    func(circle Circle) area() float64 {
       return math.Pi * circle.radius * circle.radius
    }

    /* define a method for rectangle (implementation of Shape.area())*/
    func(rect Rectangle) area() float64 {
       return rect.width * rect.height
    }

    /* define a method for shape */
    func getArea(shape Shape) float64 {
       return shape.area()
    }

    func main() {
       circle := Circle{x:0,y:0,radius:5}
       rectangle := Rectangle {width:10, height:5}

       fmt.Printf("Circle area: %f\n",getArea(circle))
       fmt.Printf("Rectangle area: %f\n",getArea(rectangle))
    }

当上述代码编译和执行时，它产生以下结果：

    Circle area: 78.539816
    Rectangle area: 50.000000

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言接口](##)


