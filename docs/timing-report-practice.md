# 简化 Timing Report 练习

下面是一个虚构的 timing report，用来练习直觉，不代表真实工具格式。

## Setup paths

| Path | Required time | Arrival time | Slack | Result |
| --- | ---: | ---: | ---: | --- |
| count_reg[0] -> count_reg[1] | 10.00 ns | 2.10 ns | +7.90 ns | PASS |
| count_reg[3] -> count_reg[4] | 10.00 ns | 4.80 ns | +5.20 ns | PASS |
| count_reg[7] -> count_reg[0] | 10.00 ns | 10.35 ns | -0.35 ns | FAIL |

## Hold paths

| Path | Required hold | Arrival time | Slack | Result |
| --- | ---: | ---: | ---: | --- |
| count_reg[2] -> count_reg[3] | 0.10 ns | 0.28 ns | +0.18 ns | PASS |
| count_reg[5] -> count_reg[6] | 0.10 ns | 0.07 ns | -0.03 ns | FAIL |

## 练习问题

1. 哪条 setup path 最危险？
2. 哪条 hold path 有问题？
3. 如果把 clock period 从 10ns 放宽到 12ns，setup slack 会怎么变？
4. 如果 routing 让某条线更长，arrival time 可能怎么变？
5. 为什么 setup 修复常常关注“让路径更快”，hold 修复有时反而要“让路径别太快”？

## 参考答案

1. `count_reg[7] -> count_reg[0]`，因为 slack 是 `-0.35 ns`。
2. `count_reg[5] -> count_reg[6]`，因为 hold slack 是 `-0.03 ns`。
3. setup required time 变大，setup slack 通常会增加。
4. arrival time 可能增加，setup slack 可能变差。
5. setup 要赶上下一个时钟沿，路径太慢会出问题；hold 要在当前采样后保持一段时间，路径太快也可能出问题。
