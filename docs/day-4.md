# Day 4：理解综合

## 45 分钟任务

不要先装综合工具。今天用文字和结构图理解：综合会把 `counter.v` 变成什么。

## Counter 的门级结构想象

```text
                 +-------------+
enable --------> |             |
count[7:0] ----> | +1 / hold   | ----> next_count[7:0]
                 | logic       |
                 +-------------+
                         |
                         v
clk -------------> 8-bit register ----> count[7:0]
rst_n -----------> reset control
```

## 今天只需要懂到这里

综合不是“运行代码”，而是把 Verilog 描述转换成硬件结构。

`always @(posedge clk ...)` 通常会推断出触发器。  
`count + 1` 会推断出加法逻辑。  
`if (!rst_n)` 会推断出复位控制。

## 今日产出

在 `notes/day-4.md` 写：

- counter 可能综合出哪些硬件块
- 哪一行代码对应触发器
- 哪一行代码对应组合逻辑

## 复习题

1. 综合和仿真有什么区别？
2. `always @(posedge clk...)` 为什么通常意味着寄存器？
3. `enable` 可能被综合成什么控制结构？
