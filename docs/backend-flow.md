# 数字后端大图

数字后端可以先理解成：把“逻辑描述”变成“芯片上真实可制造的物理实现”。

## 一条简化流程

```text
RTL
  -> synthesis
  -> gate-level netlist
  -> floorplan
  -> placement
  -> clock tree synthesis
  -> routing
  -> static timing analysis
  -> signoff
```

## 每一步在干什么

- `RTL`：用 Verilog/SystemVerilog 描述电路行为，比如 counter 怎么加 1。
- `synthesis`：把 RTL 变成标准单元组合，比如触发器、加法器、与门、或门。
- `netlist`：门级连接表，描述哪些单元和哪些线连在一起。
- `floorplan`：决定芯片区域、宏单元、电源、I/O 的大致摆放。
- `placement`：把标准单元放到具体位置。
- `CTS`：构建时钟树，让时钟尽量稳定地到达各个触发器。
- `routing`：真正连线。
- `STA`：检查信号能不能在时钟要求内按时到达。
- `signoff`：做最终检查，比如 DRC、LVS、功耗、时序。

## 本周只抓住一句话

后端不是“画线”，而是在面积、功耗、时序、可制造性之间做收敛。
