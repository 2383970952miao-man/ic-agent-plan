# Day 2：写第一个 Verilog 模块

## 45 分钟任务

阅读 `src/counter.v`，然后回答：

1. `clk` 是什么？
2. `rst_n` 为什么带 `_n`？
3. `enable` 为 0 时，`count` 为什么保持不变？
4. `count <= count + 8'd1;` 表示什么硬件行为？

## 今天只需要懂到这里

这个 counter 本质上是：

```text
8 个触发器 + 一个加 1 的组合逻辑 + reset/enable 控制
```

你先不需要写复杂 Verilog，只要能读懂这个模块。

## 今日产出

在 `notes/day-2.md` 写：

- counter 的输入输出说明
- reset 时发生什么
- enable 时发生什么
- 我觉得最陌生的一行代码

## 复习题

1. `reg [7:0] count` 为什么是 8 位？
2. `posedge clk` 和普通 if 判断有什么区别？
3. 如果 `enable` 一直为 1，`count` 从 255 后会变成多少？
