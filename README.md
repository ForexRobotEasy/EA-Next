# EA Next ReadMe File

This ReadMe file provides a detailed description of the code for the EA Next Forex Trading Software. This code includes the necessary trading functions and code requirements to implement the algorithm and required features of the software.

## Inputs

The code includes the following inputs:

1. `LotSize` (default = 0.01): Specifies the lot size for trading.
2. `UseFixedLot` (default = false): Specifies whether to use a fixed lot size for trading.
3. `StopLoss` (default = 50.0): Specifies the stop loss value in points.

## Global Variables

The code includes the following global variables:

1. `averagePrice`: Stores the average price during trading.
2. `deviationThreshold` (default = 10.0): Specifies the deviation threshold for the trade closing algorithm.

## Functions

### CalculateLotSize()

This function calculates the lot size based on the account equity. If `UseFixedLot` is enabled, it returns the fixed lot size specified by `LotSize`. Otherwise, it calculates the lot size based on the account equity, risk percentage, and stop loss value.

### CloseTrades()

This function is responsible for closing trades based on the trade closing algorithm. It iterates through all open trades and checks if the trade's open price deviates from the average price by more than the `deviationThreshold`. If the trade is profitable, it is closed at the current bid price, and if it is in a loss, it is closed at the current ask price.

### ManageRisk()

This function manages the risk by setting the stop loss for each trade. It iterates through all open trades and checks if the trade's stop loss is not set. If it is not set, it modifies the trade's stop loss to be `StopLoss` points below the open price.

### OnTick()

The `OnTick()` function is the entry point of the EA Next software. It performs the following tasks:

1. Checks if the current symbol is USDCHF. If not, it displays a message recommending optimization for other currency pairs.
2. Checks if the current timeframe is M5. If not, it displays a message recommending adaptation for other timeframes.
3. Calculates the lot size using the `CalculateLotSize()` function.
4. Opens new trades by sending buy and sell orders at the current ask and bid prices, respectively, with the specified lot size and stop loss.
5. Calls the `CloseTrades()` function to close trades based on the trade closing algorithm.
6. Calls the `ManageRisk()` function to manage risk by setting stop loss for each trade.

## Product Description

EA Next is a Forex Trading Software developed by Forex Robot Easy Team. It is designed to implement a strategic trading algorithm for optimal trading results. The software uses a combination of technical indicators and risk management techniques to identify trading opportunities and manage risk effectively.

Key Features:
- Flexible lot size options: Choose between a fixed lot size or calculate it based on account equity and risk percentage.
- Intelligent trade closing algorithm: Close trades based on a deviation threshold from the average price, ensuring profitable trades are closed at the optimal price.
- Risk management: Set stop loss for each trade to manage risk effectively.

Please note that ForexRobotEasy is not the official developer of this product. This code is provided as a sample that can work as described in the product. For detailed reviews and trading results of this product, please visit the official developer's site at [EA Next Review - Strategic Forex Software for Optimal Trading](https://forexroboteasy.com/forex-robot-review/ea-next-review-strategic-forex-software-for-optimal-trading/).

For more information and to obtain the official version of this product, please visit the MQL5 website.
