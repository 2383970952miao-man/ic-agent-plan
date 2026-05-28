# Day 5：理解时钟约束和 STA

## 45 分钟任务

今天只学 4 个词：

- `clock period`
- `setup`
- `hold`
- `slack`

## 用 counter 理解

一次计数可以想象成：

```text
旧 count 从寄存器出来
  -> 经过 +1 组合逻辑
  -> 新 count 必须在下一个时钟沿前稳定
  -> 下一个时钟沿被寄存器采样
```

如果时钟周期太短，`+1` 逻辑和连线延迟来不及完成，就会出现 setup violation。

## 最小定义

- `clock period`：两个时钟上升沿之间的时间。
- `setup`：数据要在采样时钟沿之前提前稳定。
- `hold`：数据要在采样时钟沿之后继续保持一小段时间。
- `slack`：剩余时间。正数通常表示够用，负数表示违例。

## 今日产出

在 `notes/day-5.md` 写：

- 我用自己的话解释 setup
- 我用自己的话解释 hold
- 我用自己的话解释 slack
- 如果 slack 是负数，我会怎么理解

## 复习题

1. 时钟越快，对 setup 越友好还是越苛刻？
2. slack = -0.12ns 意味着什么？
3. 为什么 routing 之后 timing 可能变差？
