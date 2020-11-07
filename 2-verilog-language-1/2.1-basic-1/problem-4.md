## **Problem 3 :** Wire4

前文中我们讨论过，wire 的源一般只能有一个，终点确可以有多个。一个源可以驱动多个信号。本题中，我们要使用三个信号源 a,b,c 驱动四个信号 w,x,y,z.

* a -&gt; w
* b -&gt; x
* b -&gt; y
* c -&gt; z

![](https://pic2.zhimg.com/80/v2-ef61f9855b5e11b45415da5d680f6591_720w.jpg)

从模块的角度来说，有三个输入端口和四个输出端口，上图给出了信号的流向。

当你使用多条 assign 语句时，他们之间的顺序是无关紧要的，这点同顺序执行的软件代码不同。事实上，大部分 Verilog 代码之间的**顺序都不会对结果产生影响**。assign 描述的是端口之间的连接关系，而不是一次复制右值，赋给左值的复制黏贴，连接关系不存在先后之分。

这里要澄清一个容易混淆的概念，图中的绿线代表的是 wire 之间的连接，而不是 wire 本身。即 wire 是连线两端的信号，而不是连线本身。上图中的模块实际声明了 7 个 wire 信号\(a, b, c, w, x, y, z\)。这是因为模块的输入输出端口实际上都是 wire。

我们一般这么声明端口信号

> input a;

但实际上我们声明的是

> input wire a;

所以，assign 语句并不是创建 wire ，而是将创建 wire 之间的连接。

### **解答与分析**

```
module top_module (
	input a,
	input b,
	input c,
	output w,
	output x,
	output y,
	output z  );
	
	assign w = a;
	assign x = b;
	assign y = b;
	assign z = c;
	
endmodule

```

wire 是信号，而 assign 语句则建立了信号之间的连接，这种连接是有方向性。

模块的输入输出端口也同样是 wire 类型的。



