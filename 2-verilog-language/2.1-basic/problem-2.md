## **Problem 2 :** Wire

这题中我们将认识到 Wire，Verilog 中重要的一种**信号（Signal）**类型，我们将通过建立一个模块 \(module\) 来实现 wire。所谓模块就是前两题中我们构建的东西，拥有输入输出端口的黑盒，在之后我们会详细讲解模块，

wire 的中文可以翻译为导线，但 Verilog 中的 wire 和中文语境中的导线不是一回事。wire 应该理解为一个**信号**，信号是有**方向性**的。

wire 信号可能从 A 点输出，输入到 B 点和 C 点。wire 一般只有一个 source，即从某一点输出，但可以有多个 sinks，即输入到多个点。A 点通常会被称为一个驱动（driver），把某个数值驱动到 wire 信号上。

模块中的端口也带有方向性，主要分为输入 input 和输出 output 端口。输入端口是由模块外部的信号驱动的，而输出端口则又会驱动另一个外部信号。

如果我们通过一个模块来模拟 wire 信号的行为，那么从模块内部来看，输入端口就信号的源或者驱动（source/driver），而输出端口则是信号的终点（sink）。

把驱动的概念引进到 Verilog 中，可以写作：

`assign left_side = right_side;`

right\_side 的值就被驱动到 left\_side 中，以上的语法结构名为**连续赋值**（continous assignment）。但请注意与软件中的赋值操作做区分，Verilog 中的赋值是使用一条带有方向的导线连接了两个信号，所以 left\_side **始终等于** right\_side，随 right\_side 变化而变化。而软件中的赋值是一种事件，某个时刻 left\_side 的值变成了和 right\_side 相同的值。![](https://pic4.zhimg.com/80/v2-c81b98808c6864e99117f37f438aff3f_720w.jpg)

_图片来自 HDLBits_

通过上图我们可以了解到电路的各个部分是如何与 Verilog 代码所一一对应的。

代码中已有的模块和端口声明语句已经构建出电路中的黑框部分。黑框以及箭头分别代表模块和端口。而外部的驱动信号和模块下游的信号也已经给出，即图中灰色的部分。你要做的工作是完成图中**绿色的部分**，即完成这条连线。

你可以在模块体中**使用一条 assign 语句**，将**输入端口连接至输出端口**来完成这个模块。端口也可以理解为是一个 wire 信号，assign 用于实现 wire 信号间的连线。

你不需要实现黑框外部的信号，将会由我们来完成，但你需要意识到那些信号是用于测试你的模块。

除了**连续赋值**，Verilog 还有三种其他的赋值方式，这三种赋值方式都只能在过程块中使用，我们将在后续的题目中讨论。

### **解答与分析**

```Verilog
module top_module( input in, output out );
    assign out = in;
// Note that wires are directional, so "assign in = out" is not equivalent.
//注意 wire 是有方向的 因此 assign in = out 是不等价的
endmodule
```

代码非常简洁，但始终要注意思考代码和电路，和上图中模块描述的关联。

另外 wire 是 Verilog 中的一种数据类型，代表的是**信号**，而不是连线。

在这里可以对 module 和连续赋值抱有疑惑，我们将在后续的内容中继续讨论。

