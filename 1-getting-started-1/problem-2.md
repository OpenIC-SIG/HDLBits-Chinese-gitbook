## **Problem 1 :** Zero

这题同样要求构建一个电路，没有输入端口，只有一个输出端口，但这次输出端口时钟驱动逻辑 0 ，如果你完成了前一道题，那么这题也自然不在话下。

部分题目提供了 Hint，可以给你提供一些帮助。

比如这题的提示：如果你什么也不做，在 Quartus 中，输出端口会被默认赋值为 0，所以这题超简单，直接提交即可。（当然，使用默认值是危险，相当不推荐的行为）

### **解答与分析**

```Verilog
module top_module
(
    output zero
);
// Module body starts after semicolon

assign zero = 1'b0;

endmodule
```



