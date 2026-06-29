# cTrader Position Manager & Advanced Risk Management Tool

Welcome to the official documentation repository for the **AlgoCreators Position Manager**—a next-generation utility and indicator designed natively for the **cTrader (cAlgo)** platform. 

This tool is engineered for professional traders, algorithmic scalpers, and prop firm funded traders who require precision execution, instantaneous risk calculation, and bulletproof account protection.

---

## 📸 Interface Overview

Below is the layout of the Position Manager. You can completely toggle, minimize, or customize each panel directly from the indicator's main settings to fit your trading style.

> 💡 *To drag and move the entire setup, click the **4-directional arrow button** located at the top-left of the Main Panel and click again.*

![cTrader Position Manager Interface](https://github.com/AlgoCreators/ctrader-position-manager/blob/main/Position%20manager%20interface.jpg)
---

## 1. Main Panel (Market & Pending Orders)
The Main Panel consists of two primary tab: **Market Order** and **Pending Order**. Clicking on the header of the active tab will instantly minimize the panel.

* **Dynamic Order Direction:** The Buy/Sell buttons activate automatically based on your Stop Loss (SL) line. If the red SL line is above the current market price, it switches to **Sell**. If it is below, it switches to **Buy**.
* **Instant Switch:** A centralized switch button allows you to flip the trade direction instantly.
* **Flexible Risk Allocation:** Define your risk per trade by clicking the blue toggle switch next to the Risk input field:
  * `$` (Fixed USD/Account Currency Amount)
  * `%` (Percentage of Account Balance)
  * `V` (Custom Volume/Lot Size)
* **Target Reward:** Set your Take Profit (TP) dynamically using either **Risk-to-Reward Ratio (RR)** or absolute **Pips**.
* **ATR Placement:** Click the **ATR button** to automatically project your Stop Loss based on the current market Average True Range (ATR). Use the up/down arrows to multiply or divide the ATR coefficient instantly.
* **Fixed Pip Stop Loss:** Next to the ATR option, you can lock your SL to a fixed pip value (e.g., inputting `100` ensures every trade initializes with a 100-pip Stop Loss).
* **Order Comments:** Add custom tags in the `Comment` box, which will be logged directly into your cTrader transaction history.

---

## 2. Partial Panel (Pre-Trade Automation)
This panel handles advanced trade management rules **before** an order is executed.

> ⚠️ **Crucial Operational Requirement:** For partial executions, trailing stops, and break-even triggers to function, your trading terminal must remain open, connected to the internet, and the indicator must be active. The indicator manages these lines locally.

### 🔹 Partial Take Profit (Partial TP)
Set up to 3 automated partial profit targets prior to trade execution:
* Click **TP1**, **TP2**, or **TP3** to deploy a target line on your chart.
* **Left Input Field:** Defines the volume to close (toggle between `%` of the position or specific `Lot` sizes).
* **Right Input Field:** Defines the execution level (toggle between **RR** or **Pips**).

### 🔹 Partial Stop Loss (Partial SL)
Set up to 3 automated risk-reduction levels to lock in partial losses or secure partial wins if the trade turns around. (By default, lines 2 and 3 are hidden but can be enabled via settings).
* Features identical dual-box inputs (`%`/`Lot` and `RR`/`Pip`) just like the Partial TP settings.

### 🔹 Break Even & Trailing Stop Triggers
* **Trigger BE:** Deploy a pre-trade Break-Even line based on RR or Pips. Once hit, your SL moves automatically to your entry price.
* **Trigger TS:** Deploy a pre-trade Trailing Stop activation line based on RR or Pips.

> 🛠️ **On-Chart Flexibility:** Once a trade is live, you can manually drag any partial line with your mouse. To delete a specific partial setup, simply select the line on the chart and press the **Delete** key.
> 👁️ **Clean Charts Feature:** Active live partials add a small `Partials` button on your entry line. Click it to quickly toggle the visibility of your management lines. *Note: Hidden lines will still execute perfectly.*

---

## 3. Advance Panel (Live Position Management)
Designed specifically to manage open exposure and running positions. It is split into two halves: Upper management tools and a Lower live positions table.

* **Performance Optimization:** The live position table can be disabled in the settings for heavy-frequency traders managing dozens of concurrent orders to save screen estate.
* **Add Partials Dynamically:** Select an active trade from the list, click `+TP` or `+SL`, and move your mouse on the chart to drop a new partial line on the fly (Max 3 TPs and 3 SLs per live trade).
* **Securing Profits:** If a trade is in deep profit, you can drag and drop a new `+SL` partial line inside the profit zone to lock in gains.
* **On-the-Fly Triggers:** Instantly inject a `+Trigger TS` or `+Trigger BE` to any running trade.
* **Bulk Executions:** Select multiple live trades and click:
  * `TS` to activate native trailing loops.
  * `BE` to move all winning trades to Risk-Free instantly.
  * `25%` / `50%` / `75%` to immediately liquidate a fraction of the selected positions.
  * `Close` to kill the selected exposures entirely.
* **Selection Modes:** Select positions directly from the built-in lower grid panel or via the drop-down menu on the left side of the panel.

---

## 4. Details Panel (Account Analytics & Prop Protection)
Divided into two professional vertical tabs:

### 📊 Trading Details
Displays real-time telemetry metrics:
* Total aggregated risk on open positions.
* Total risk on pending limits/stops.
* Net PnL breakdowns calculated for the Current Day, Current Week, and Current Month.

### 🛡️ Prop Settings (Hard Drawdown Protections)
Set mathematical kill-switches on your trading account to pass prop firm challenges and prevent catastrophic days:
* **Max Daily Profit Target**
* **Max Daily Loss Limit**
* **Max Open Account Exposure (Risk)**

Using the drop-down menu under each protective option, you can program the indicator's behavior upon breach:
1. *Show Warning Only* (Displays a UI alert).
2. *Close Trades & Show Warning* (Instantly liquidates all market exposure and restricts trading).
3. *Do Nothing*.

---

## ❓ Frequently Asked Questions (FAQ)

| Question | Answer |
| :--- | :--- |
| **Can I open trades without a Take Profit (TP)?** | Yes. Simply click the `X` button directly on the chart's TP line to remove it. To reactivate it later, click the `Enable TP` button on the Main Panel. |
| **Can I open trades without a Stop Loss (SL)?** | **No.** To maintain mathematical validity and leverage the position sizing engine, an SL is strictly mandatory. Removing the SL breaks core account equity features. |
| **What are the diamond icons on the chart lines?** | These are anchor points acting as "line twins." They allow you to easily grab, drag, and drop SL/TP lines even on cluttered, high-density charts without miss-clicking. |
| **Can I manually override the automated TP placements?** | Yes. By default, the TP line snaps to the math on the Main Panel. Click the `Auto` button attached to the TP line on your chart to switch it to `Manual` mode, allowing free-hand placements. Click `Manual` to snap it back to auto. |

---

## 💾 Saving Your Presets Fast
To save your customized panel locations, toggle states, and on-chart configurations as the universal default layout, press **`Shift + S`** on your keyboard. 

Any new chart you open will instantly load with your exact personalized workspace setup. *(Note: Master core properties of the indicator should still be saved via the standard cTrader settings menu).*

---

---

## 🛠️ Installation Guide

Installing the Position Manager in cTrader is quick and requires no coding knowledge. Follow these simple steps:

1. **Download the File:** Get the official `.algo` file from our website.
2. **Install to cTrader:** Double-click the downloaded `.algo` file. cTrader will automatically open and install the tool into your platform.
3. **Deploy on Chart:** 
   * Open cTrader and right click on the chartt on the **Indicators** menu .
   * Find **Position Manager**.
   * Click on it and then click the "Add to Chart" button.

---

## 📘 Full Documentation & Downloads
For the complete technical manual, advanced partial trailing logic parameters, custom hotkey configurations, and to download the trial or premium versions, please visit the official product page:

👉 [Get Full cTrader Position Manager Guide & Download on AlgoCreators.net](https://algocreators.net/en/portfolio/position-manager-indicator-ctrader/)

***
*Developed by [AlgoCreators](https://algocreators.net) — Premium Algorithmic Tools for Professional Traders.*
