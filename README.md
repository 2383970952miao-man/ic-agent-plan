# 数字后端 + Agent 七天启动项目

这个小项目的目标不是学完数字后端，而是在 7 天内跑通一个轻量闭环：

`Verilog 小电路 -> 测试思路 -> 综合结构理解 -> 时序概念 -> 简化后端报告 -> 作品集笔记`

第一周不强行安装复杂工具。你可以直接阅读代码和任务卡，用 Codex/Claude Code 陪你完成每一天。

## 项目结构

- `src/counter.v`：8-bit counter 主模块
- `tb/tb_counter.v`：测试平台示例
- `scripts/counter_model.py`：不用 Verilog 工具也能跑的计数器行为模型
- `docs/day-*.md`：7 天任务卡
- `docs/agent-prompts.md`：每天可直接复制给 agent 的提示词
- `docs/backend-flow.md`：数字后端大图
- `docs/timing-report-practice.md`：简化 STA 报告练习
- `docs/portfolio-note-template.md`：第 7 天作品集笔记模板

## 今天就怎么开始

1. 打开 `docs/day-1.md`。
2. 只做里面的 45 分钟任务。
3. 卡住时复制 `docs/agent-prompts.md` 里的提示词问 Codex/Claude Code。
4. 每天结束时，把当天笔记写到 `notes/day-1.md` 这种文件里。

## 本周成功标准

- 第 3 天：能说清楚 counter 的输入、输出、时钟、复位。
- 第 5 天：能用自己的话解释 `setup`、`hold`、`slack`。
- 第 7 天：有一份可以展示的 README 小笔记，而不是只“看过课”。

## 可选：运行轻量行为模型

如果你的机器有 Python，可以运行：

```bash
python3 scripts/counter_model.py
```

这不是 Verilog 仿真，只是帮助你先理解 counter 在时钟和 reset 下应该怎么变化。
