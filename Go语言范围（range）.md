`range`关键字在`for`循环中用于遍历数组，切片，通道或映射的项目。 使用数组和切片，它返回项的索引为整数。 使用映射则它返回下一个键值对的键。 范围返回一个或两个值。如果在范围表达式的左侧仅使用一个值，则它是下表中的第一个值。

| 范围表达式        | 第1个值     | 第2个值(可选)  |
|-------------------|-------------|----------------|
| 数组或切片a\[n\]E | 索引 i 整数 | a\[i\]E        |
| Strubg s字符串    | 索引 i 整数 | 符文整数       |
| map m map\[K\]V   | key k K     | value m\[k\] V |
| channel c chan E  | element e E | none           |

<a href="" class="reference-link"></a><span class="header-link octicon octicon-link"></span>示例
------------------------------------------------------------------------------------------------

以下是范围应用的一些示例：

    package main

    import "fmt"

    func main() {
       /* create a slice */
       numbers := []int{0,1,2,3,4,5,6,7,8} 

       /* print the numbers */
       for i:= range numbers {
          fmt.Println("Slice item",i,"is",numbers[i])
       }

       /* create a map*/
       countryCapitalMap := map[string] string {"France":"Paris","Italy":"Rome","Japan":"Tokyo"}

       /* print map using keys*/
       for country := range countryCapitalMap {
          fmt.Println("Capital of",country,"is",countryCapitalMap[country])
       }

       /* print map using key-value*/
       for country,capital := range countryCapitalMap {
          fmt.Println("Capital of",country,"is",capital)
       }
    }

当上述代码编译和执行时，它产生以下结果：

    Slice item 0 is 0
    Slice item 1 is 1
    Slice item 2 is 2
    Slice item 3 is 3
    Slice item 4 is 4
    Slice item 5 is 5
    Slice item 6 is 6
    Slice item 7 is 7
    Slice item 8 is 8
    Capital of France is Paris
    Capital of Italy is Rome
    Capital of Japan is Tokyo
    Capital of France is Paris
    Capital of Italy is Rome
    Capital of Japan is Tokyo

本文属作者原创，转载请注明出处：[易百教程](http://www.yiibai.com) » [Go语言范围（range）](##)


