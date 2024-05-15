# Lab1

## 简答作业

1. RustSBI version 0.3.0-alpha.2, adapting to RISC-V SBI v1.0.0
- PageFault in application, bad addr = 0x0, bad instruction = 0x804003ac kernel killed it.
- IllegalInstruction in application, kernel killed it.
- IllegalInstruction in application, kernel killed it.

2.1. 内核栈栈顶;运行某应用或在执行完 trap 后返回U 态的地址
2.2. t0\t1\t2 为临时寄存器，用来保存 3 个值，这三个值分别被赋值给 sstatus\sepc\sscratch 这三个 CSR。sstatus 表示恢复之后的 CPU 处于哪个特权级，sepc 表示 Trap 之前最有一条指令的地址，sscratch 表示用户栈栈顶

3. 跳过 x2 是为了基于它来找到每个寄存器应该被保存到的正确的位置，跳过 x4 是因为除非我们手动出于一些特殊用途使用它，否则一般也不会被用到

4. sp 指向内核栈，sscratch 指向用户栈

5. sret，这条指令的作用就是退出 S 态，我们从 U 态进入的 S 态，在退出 S 态后会进入 U 态

6. sp 内核栈，sscratch 用户栈

7. ecall

## 荣誉准则

1. 在完成本次实验的过程（含此前学习的过程）中，我曾分别与 以下各位 就（与本次实验相关的）以下方面做过交流，还在代码中对应的位置以注释形式记录了具体的交流对象及内容：

nobody

2. 此外，我也参考了 以下资料 ，还在代码中对应的位置以注释形式记录了具体的参考来源及内容：

https://learningos.cn/rCore-Tutorial-Guide-2024S/chapter3/5exercise.html
https://learningos.cn/rCore-Tutorial-Book-v3/chapter2/0intro.html


3. 我独立完成了本次实验除以上方面之外的所有工作，包括代码与文档。 我清楚地知道，从以上方面获得的信息在一定程度上降低了实验难度，可能会影响起评分。

4. 我从未使用过他人的代码，不管是原封不动地复制，还是经过了某些等价转换。 我未曾也不会向他人（含此后各届同学）复制或公开我的实验代码，我有义务妥善保管好它们。 我提交至本实验的评测系统的代码，均无意于破坏或妨碍任何计算机系统的正常运转。 我清楚地知道，以上情况均为本课程纪律所禁止，若违反，对应的实验成绩将按“-100”分计。
