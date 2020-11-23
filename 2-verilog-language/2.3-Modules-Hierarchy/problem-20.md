# Problem 20: Module pos

本题与前一个问题`(Problem 19: Modules)`相似。给出了一个名为`mod_a`的模块，该模块按顺序具有2个输出和4个输入。必须将6个端口按位置顺序与顶层的端口`out1, out2, a, b, c`和`d`相连接。

![](https://hdlbits.01xz.net/mw/images/b/b7/Module_pos.png)

给出的模块如下：

```verilog
module mod_a ( output, output, input, input, input, input );
```

**解答与分析**

```verilog
module top_module ( 
    input a, 
    input b, 
    input c,
    input d,
    output out1,
    output out2
);

    mod_a name(out1,out2,a,b,c,d);
    
endmodule
```

从`Problem 19`开始进入了模块层次类，主要考查的是模块之间的连接问题，模块之间有两种连接模式，在`Problem 19`中应该已经尝试过这两种连接模式了。

但是在本题中对于给出的模块来说，我们并不知道`mod_a`这个模块的端口名是什么，所以对于本题来说，只能按照位置的顺序来连接。

对于题中给出的模块来说，如果在写文档的时候这样只表注输入输出端口而没有名字是不规范的。自己写文档的时候要避免。