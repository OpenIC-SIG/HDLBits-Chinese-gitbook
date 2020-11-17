## **Problem 2 :** Wire

这题中我们将认识到 Wire，Verilog 中重要的一种**信号**类型，我们将通过建立一个模块 \(module\) 来实现 wire。所谓模块就是前两题中我们构建的东西，拥有输入输出端口的黑盒，在之后我们会详细讲解模块，

wire 的中文可以翻译为导线，但 Verilog 中的 wire 和现实中的导线不同，wire 应该理解为一个**信号**，信号是有方向性的，wire 从 A 点输出，输入到 B 点和 C 点。wire 一般只有一个 source，即从某一点输出，但可以有多个 sinks，即输入到多个点。A 点通常会被称为一个驱动（driver），把某个值驱动到 wire 上。

把驱动的概念引进到 Verilog 中，可以写作：

`assign left_side = right_side;`

 right\_side 的值就被驱动到 left\_side 中，以上的语法结构名为**连续赋值**（continous assignment）。但请注意与软件中的赋值操作做区分，Verilog 中的赋值是使用一条带有方向的导线连接了两个信号，所以 left\_side **始终等于** right\_side，随 right\_side 变化而变化。而软件中的赋值是一种事件，某个时刻 left\_side 的值变成了和 right\_side 相同的值。

模块中的端口也带有方向性，主要分为输入 input 和输出 output 端口。输入端口是由模块外部的信号驱动的，而输出端口则又会驱动另一个外部信号。如果我们通过一个模块来模拟 wire，那么从模块内部来看，输入端口就直接驱动输出端口。

![](https://pic4.zhimg.com/80/v2-c81b98808c6864e99117f37f438aff3f_720w.jpg)

_图片来自 HDLBits_

我们的题目和上图息息相关，模块和端口已经被定义好了，黑色的框图以及箭头代表模块和端口。而外部的驱动信号和模块下游的信号也已经给出，即图中灰色的部分。你要做的工作是完成图中**绿色的部分**，即完成这条连线。

你可以在模块体中**使用一条 assign 语句**，将**输入端口的值赋给输出端口**来完成这个模块。你不需要考虑黑框外部的信号，那些事用来测试你模块的信号，将会由我们来完成。

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

