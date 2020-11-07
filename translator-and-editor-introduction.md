作者最初被安利了一个很棒的 Verilog 学习网站：HDLBits 。然后发现知乎上还没有与 HDLBits 相关的话题，便写下知乎《HDLBits中文导学》专栏中的的第一篇文章《HDLBits: 在线学习 Verilog （〇）》向大家推荐 HDLBits。

之后，我在做题时突然产生了一个想法，可以在做题的同时，将题目翻译成中文，并结合自己做题的思路，同时附上解决问题中查阅整理的相关数字电路知识，形成一系列的专题文章。

文章发布后，在知乎得到了不错的反响，后来有更多的小伙伴参与到专栏的建设当中，截止目前我们已经完成了大约 2/3 的工作，得到了很多积极的评论和点赞。我们为帮助到了一些读者而感到非常高兴。最后，感谢大家伙的支持，希望我们能早日填坑成功！

![](https://pic2.zhimg.com/80/v2-6e93cba897b5cb258753fb7239611e51_720w.jpg)

## **Verilog 基础教程**

HDLBits 有一系列的 Verilog 基础知识，从最简单的 wire 的概念开始，包括了 Verilog 的基础语法，由逻辑门与触发器组成的电路，组合时序电路的概念，模块层级概念，testbench 的编写等等。下图是整体的层级目录。

![](https://pic4.zhimg.com/80/v2-80b84189ce69c7c50087b39c8afd9697_720w.jpg)

完整地对 Verilog 的语法进行整理就已经很棒了，我一直没有发现这样系统整理 Verilog 语法的中文网站，比如像菜鸟教程这样的网站，提供了大量软件语言的语法学习与备忘查询，大多数语言还支持在线编译执行。

![](https://pic3.zhimg.com/80/v2-3c96a8ef5f84ec2207e2f1f30a038aa6_720w.jpg)

Verilog 语法不是最重要的事，更重要地是能够对代码进行在线仿真。

## **Verilog 在线仿真**

HDLBits 还提供了类似上图中，在线执行 c 语言代码的功能，可以在线对 Verilog 代码进行仿真，观察输出的时序。

比如在 Wire 的教程中，就需要你实现一个模块，实现 wire 连线的功能。

![](https://pic3.zhimg.com/80/v2-4aa5d212f6b904f4df92aea6e4509522_720w.jpg)

假如今日你的心情非常糟糕，错写成 assign out = ~ in; 那么提交之后，网站会指出你的时序同正确时序的差异：

![](https://pic3.zhimg.com/80/v2-89f36fd672e5d2a0b719fd82f6afaf76_720w.jpg)

## **举个例子**

每个知识条目下，基本都有相应的练习，比如这个计数器。

![](https://pic1.zhimg.com/80/v2-bf4055fa9ece3f724dc0bd68da8980f8_720w.jpg)

如果你突然发现自己有点不确定怎么实现这个计数器了，那赶紧上 HDLBits 操练下吧。

[Wire - HDLBits​](https://link.zhihu.com/?target=https%3A//hdlbits.01xz.net/wiki/Wire)

另外，简单注册之后，你的程序和进度就可以保存了。

## **关于我们**

我和几位小伙伴一起整理翻译了 HDLBits 的题目（目前完成 2/3 了）,附上了我们的答案与解析，以及随手穿插其中有关 Verilog 的理解分享。收录在我们的专栏：HDLBits 中文导学 中。欢迎关注，点赞，并向我们投稿你有关 Verilog，HDLBits 的相关见解！

## **声明**

我们和作者邮件通信过，我们涉及 HDLBits 的中文翻译，图片应用以及解析一般版权问题。

转载最好请注明原作者和我们二次创作的链接。对 HDLBits 本身的再创作，最好可以联系下原作者。

[HDLBits 中文导学​](https://zhuanlan.zhihu.com/c_1131528588117385216)

[zhuanlan.zhihu.com](https://zhuanlan.zhihu.com/c_1131528588117385216)

作者: ljgibbslf@zhihu

邮箱:lf\_gibbs@163.com

