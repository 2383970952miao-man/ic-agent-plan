# 我第一次理解数字后端流程：从 8-bit counter 到 timing slack

## 1. 我做了什么

这一周我用一个 8-bit counter 作为入口，理解了数字后端从 RTL 到时序分析的大致流程。

项目包括：

- 一个 Verilog counter 模块
- 一个 testbench 示例
- 一个轻量 Python 行为模型
- 一份简化 timing report 练习
- 一套 7 天学习笔记

## 2. Counter 的功能

这个 counter 有 3 个输入和 1 个输出：

- `clk`：时钟
- `rst_n`：低有效复位
- `enable`：计数使能
- `count[7:0]`：8 位计数结果

当 reset 有效时，`count` 变成 0。  
当 reset 释放且 enable 为 1 时，每个时钟上升沿 `count` 加 1。  
当 enable 为 0 时，`count` 保持不变。

## 3. 我理解的后端流程

```text
RTL -> synthesis -> netlist -> placement -> CTS -> routing -> STA -> signoff
```

我现在的理解是：后端不是简单画线，而是把逻辑变成真实物理实现，并持续检查面积、功耗、时序和可制造性。

## 4. 我第一次理解的 STA

我现在能用自己的话解释：

- `setup`：数据要在采样时钟沿之前提前稳定。
- `hold`：数据要在采样时钟沿之后继续保持一小段时间。
- `slack`：剩余时间。正数通常表示通过，负数表示违例。

## 5. 我还不懂的问题

- 真实综合工具如何把 `count + 1` 映射成标准单元？
- OpenROAD 的 flow 脚本怎么组织？
- 真实 STA 报告里每一列具体怎么看？
- setup 和 hold violation 在真实项目里分别怎么修？

## 6. 下一步

第二周我准备从下面三条路线选一条：

- 安装 `iverilog`，先跑通 Verilog 仿真。
- 安装 `yosys`，观察 counter 的综合结果。
- 继续写一个 4-bit ALU，扩大 RTL 练习量。
