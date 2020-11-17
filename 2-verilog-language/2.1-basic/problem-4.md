## **Problem 4 :** Notgate

非门在数字电路中十分常见，本题我们要通过 assign 语句以及 Verilog 的逻辑操作符，实现一个非门模块。

![](https://pic4.zhimg.com/80/v2-c79c8e3a59dfcf46ffddb1e353f4ace3_720w.jpg)

与 wire 模块相同，非门模块中 in 被连接到 out，相比 wire 模块，唯一的区别在于：输出信号 out 是将输入信号 in 取反得到。

我们在 assign 语句中增加的逻辑操作符为 ~（**逐位取反**），由于我们的信号位宽为 1 位，我们也可以使用！（**逻辑取反**）。二者的区别在于逻辑取反的结果时钟只有一位，而逐位取反结果的位宽和输入信号位宽相同，在每一个位上逐位（bitwise）取反。

### **解答与分析**

```Verilog
module top_module (
	assign	out = ~ in;
endmodule
```

非门在 wire 的模块上稍加改造，对 assign 语句添加逻辑运算符实现。



