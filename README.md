<div align="center">

# OKX Volatility Hunter & Grid Trading Bot
### 妖币猎手 & 高频网格交易机器人

**一个为捕捉市场极端波动而生的、拥有“猎手级”智能扫描引擎的OKX现货交易机器人。**  
**A spot trading bot for OKX, engineered to capture extreme market volatility with its "Hunter-Class" intelligent scanning engine.**

</div>

<p align="center">
    <!-- Badges - 徽章 -->
    <img src="https://img.shields.io/badge/Python-3.10+-blue?logo=python" alt="Python Version">
    <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-orange" alt="Platform">
    <img src="https://img.shields.io/badge/UI-CustomTkinter-green" alt="UI Framework">
    <img src="https://img.shields.io/badge/License-MIT-purple" alt="License">
</p>

<p align="center">
  <!-- GIF DEMO - 动态图演示 -->
  <img src="https://github.com/user-attachments/assets/a71ae6e8-4795-40fc-8f3e-4accdc8cb333" alt="Bot Demo GIF" width="800">
  <br>
  <br>
</p>

<div align="center">

**Languages:**
<details open>
<summary><strong>English (Click to Expand)</strong></summary>

## Why Choose This Bot?

Most trading bots are passive. You tell them what to trade, and they execute. **This bot is a hunter.** It actively seeks out the most volatile and potentially profitable opportunities in the market for you.

| Feature                      | Standard Bots                                      | **Volatility Hunter Bot**                                                              |
| ---------------------------- | -------------------------------------------------- | -------------------------------------------------------------------------------------- |
| **Opportunity Discovery**    | ❌ Manual (User must find coins)                   | ✅ **Automatic**: "Gem Hunter" engine scans the entire market to find the best coins. |
| **Parameter Configuration**  | Manual & Complex                                   | ✅ **Intelligent**: Recommends optimized parameters based on real-time volatility.     |
| **Strategy Adaptability**    | Often rigid                                        | ✅ **Dual-Mode**: Adapts strategy (Grid/Sniper) based on your capital size.          |
| **Risk Management**          | Basic Stop-Loss                                    | ✅ **Dynamic**: High-frequency Guardian thread ensures a precise trailing stop-loss. |
| **User Experience**          | Command-line or basic UI                           | ✅ **Modern & Intuitive**: Full-featured GUI with internationalization (EN/ZH).      |

---

## In-Depth Features

### 🎯 "Gem Hunter" Scanning Engine
This is the core of the bot. It's not just a simple volume filter. The engine analyzes every USDT pair on OKX and assigns a "Volatility Score" based on a multi-factor weighted model:
-   **ATR (Average True Range)**: Measures raw price volatility.
-   **Pin Bar Analysis**: Detects assets with recent high-wick candles ("pins"), a strong indicator of volatility and liquidity battles.
-   **Trading Activity (TPM)**: Measures trades-per-minute to gauge market interest and activity.
-   **Liquidity**: Ensures the asset has enough volume for safe entry and exit.

The bot then presents you with the top-scoring asset, turning market chaos into a clear, actionable trading signal.

### 🧠 Intelligent Auto-Configuration
Stop guessing parameters. Based on the "Gem Hunter's" analysis, the bot instantly recommends a full strategy profile:
-   **Dynamic Spread & Step**: Wider spreads for highly volatile assets, tighter for calmer ones.
-   **Adaptive Grid Density**: Automatically adjusts the number of grid pairs based on capital and volatility, maximizing capital efficiency.
-   **ATR-Based Stop-Loss**: Sets a logical stop-loss distance based on the asset's actual recent volatility.

### 🛡️ Millisecond Guardian Thread
Risk management cannot be slow. The Guardian runs in a separate, high-priority thread, polling the price at a much higher frequency than the main trading loop. This decoupling ensures that your trailing stop-loss is monitored with millisecond precision, protecting your capital from sudden market crashes, independent of any other task the bot is performing.

---
<!-- Setup, Usage, and Disclaimer sections are the same, just included for completeness -->
## Installation & Setup
1.  **Clone the Repository**: `git clone https://github.com/YourUsername/YourRepoName.git`
2.  **Navigate & Create Venv**: `cd YourRepoName` and `python -m venv venv`
3.  **Activate & Install**: Activate the virtual environment and run `pip install -r requirements.txt`
4.  **Configure API**: Copy `.env.example` to `.env` and fill in your OKX API keys.
## Usage
Launch the GUI with `python okx_bot.py`. The workflow is designed to be intuitive: Scan -> Review -> Start.
## ⚠️ Disclaimer
This project is for educational purposes. Cryptocurrency trading involves significant risk. The author is not responsible for any financial losses. Use at your own risk.

</details>

<details>
<summary><strong>中文 (点击展开)</strong></summary>

## 为什么选择这个机器人？

大多数交易机器人都很被动——你告诉它交易什么，它才执行。**而这个机器人，是一个猎手。** 它主动为你出击，在整个市场中搜寻最混乱、最剧烈、也最有可能盈利的机会。

| 功能亮点                 | 普通机器人                               | **妖币猎手机器人**                                                              |
| ------------------------ | ---------------------------------------- | ------------------------------------------------------------------------------ |
| **机会发现**             | ❌ 手动选择 (用户必须自己找币)             | ✅ **全自动**: “妖币猎手”引擎扫描全市场，找到最佳交易对。                         |
| **参数配置**             | 手动设置，复杂且凭感觉                     | ✅ **智能化**: 基于实时波动率，一键生成最优参数建议。                            |
| **策略适应性**           | 通常很死板                               | ✅ **双模式**: 根据资金规模，自动切换“网格”或“狙击”策略。                        |
| **风险管理**             | 基础的固定止损                           | ✅ **动态化**: 独立的高频“守护者”线程，实现毫秒级精准追踪止损。                   |
| **用户体验**             | 命令行或简陋界面                         | ✅ **现代化**: 功能完整的图形界面，并支持中英双语切换。                            |

---

## 核心功能深度解析

### 🎯 “妖币猎手”扫描引擎
这是机器人的灵魂。它不是简单的成交量过滤器，而是对OKX上所有USDT交易对进行分析，并根据一个多因子加权模型给出一个“波动率分数”：
-   **ATR (平均真实波幅)**: 衡量原始的价格波动烈度。
-   **插针分析 (Pin Bar)**: 识别近期出现长上下影线的资产。这种“插针”行为是波动性和多空博弈的最强信号。
-   **交易活跃度 (TPM)**: 计算每分钟的成交笔数，衡量市场关注度和交投热度。
-   **流动性分析**: 确保资产有足够的深度，让大资金也能安全进出。

最终，机器人会将评分最高的“猎物”呈现在你面前，将纷繁的市场噪音，转化为一个清晰、可执行的交易信号。

### 🧠 智能化自动配置
告别猜测参数。基于“妖币猎手”的分析结果，机器人能瞬间为你推荐一整套策略档案：
-   **动态价差与步长**: 对高波动资产使用更宽的价差网，对平稳资产则更密集，以适应不同节奏。
-   **自适应网格密度**: 根据你的资金和市场波动性，自动调整网格对数，最大化资金效率。
-   **ATR动态止损**: 基于资产近期的真实波动幅度，设定一个逻辑严密的初始止损距离。

### 🛡️ 毫秒级“守护者”线程
风险管理，唯快不破。“守护者”在一个独立的、高优先级的线程中运行，它轮询价格的频率远高于主交易循环。这种“解耦”设计确保了你的追踪止损能被毫秒级精确监控，使其在市场闪崩时能第一时间保护你的本金，而不受机器人其他任务（如下单、日志记录）的任何影响。

---
<!-- 安装、使用和免责声明部分保持不变 -->
## 安装与配置
1.  **克隆仓库**: `git clone https://github.com/YourUsername/YourRepoName.git`
2.  **进入目录并创建虚拟环境**: `cd YourRepoName` 然后 `python -m venv venv`
3.  **激活环境并安装依赖**: 激活虚拟环境后运行 `pip install -r requirements.txt`
4.  **配置API**: 复制 `.env.example` 为 `.env` 并填入你的OKX API密钥。
## 使用方法
运行 `python okx_bot.py` 启动图形界面。整个工作流非常直观：扫描 -> 审查 -> 启动。
## ⚠️ 重要声明
本项目仅为技术研究目的，数字货币交易风险极高。作者对使用此软件造成的任何资金损失概不负责。请务必自行承担风险。

</details>

</div>

