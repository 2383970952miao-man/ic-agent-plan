# Day 3：写 testbench

## 45 分钟任务

阅读 `tb/tb_counter.v`，理解测试平台如何驱动 counter。

重点看 4 件事：

1. 怎么产生时钟？
2. 怎么先 reset 再 release reset？
3. 怎么打开和关闭 enable？
4. `$monitor` 打印了什么？

## 可选运行

如果已经安装了 Verilog 仿真工具，可以尝试：

```bash
iverilog -o counter_tb tb/tb_counter.v src/counter.v
vvp counter_tb
```

如果没有工具，先运行轻量行为模型：

```bash
python3 scripts/counter_model.py
```

## 今日产出

在 `notes/day-3.md` 写：

- 我如何验证 counter 是对的
- testbench 和真正电路有什么区别
- 我能解释的 3 行 testbench 代码

## 复习题

1. testbench 会被综合成真实硬件吗？
2. 为什么测试里要先 reset？
3. 如果 enable 关闭，count 应该怎么变化？
