# Four-Player-Buzzer
# 四人抢答器

> 大二上数字逻辑课程设计，基于 FPGA 的四人抢答电路，带计分和蜂鸣器提示

## 项目背景

- **课程**：数字逻辑
- **学校**：北京工业大学
- **时间**：2025.09 - 2025.12

## 功能特性

- 四人抢答，最先按下者锁定结果，其他按键无效
- 主持人控制：开始新的一轮 / 全局复位
- 计分系统：回答正确加分，错误减分（支持负数显示）
- 蜂鸣器提示：不同选手对应不同蜂鸣次数
- 数码管显示：每位选手得分用两位数码管显示（-9 到 99）
- 按键防抖：滤除机械抖动

## 技术栈

- **硬件描述语言**：Verilog
- **开发工具**：Quartus II
- **目标平台**：FPGA 实验箱
- **外设**：按键 × 6、LED × 4、蜂鸣器 × 1、数码管 × 8

## 模块设计
top_2142 (顶层)
├── frequency_divider_2142 # 时钟分频（50MHz → 1kHz / 1Hz）
├── button_Debounce_2142 # 按键消抖
├── quiz_2142 # 抢答逻辑（先到先得 + 锁定）
├── voice_2142 # 蜂鸣器控制（状态机）
├── score_indicater_2142 # 计分器（支持负数）
├── dynamic_scan_2142 # 数码管动态扫描
└── bcd_7_show_2142 # BCD 七段译码

## 如何下载验证

1. 用 Quartus II 打开工程文件
2. 编译综合，运行 `project7` 文件
3. 连接 FPGA 实验箱，下载到芯片
4. 按键测试抢答和计分功能

## 项目截图
<img width="1761" height="980" alt="image" src="https://github.com/user-attachments/assets/85de7bf1-0668-4ad8-a5fe-3e7018a752f1" />
<img width="1785" height="993" alt="image" src="https://github.com/user-attachments/assets/abe2b7bd-9fe2-45c2-807f-32eada981446" />



