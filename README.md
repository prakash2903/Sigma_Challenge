# _Sigma Internship Coding Challenge_ 🚀
## 💰💲 Algorithmic Trading Model for Portfolio Optimization:

This challenge focuses on using the **Quantrocket** platform to build a minimalist trading workflow and involves pulling daily close price data for **Apple stock** for the year **_2023_** 
and implementing a simple model to make buy orders.

<img src= "https://github.com/prakash2903/Sigma_Challenge/blob/main/img/qr.PNG" height = 300, width = 325, align=left>

<img src= "https://github.com/prakash2903/Sigma_Challenge/blob/main/img/AppleStock.PNG" height = 300, width = 425>

## Getting Started
  ☑️ Installed **QuantRocket** using **Docker**.

  ☑️ Went through tutorials to understand basic platform capabilities.

  ☑️ Pulled daily close price data for Apple stock (AAPL) for the year 2023 (01-01-2023 to 12-31-2023).

# Daily Stock Trading Prompt:
### 🎯 Objective : To build a model for making trading decisions (placing buy orders) on certain days in a year.
* Aims to 📈 maximize the portfolio value by deciding whether to place a buy order trade for the next day.
* Uses daily **_close prices (p(d))_** and calculates **_percentage returns (r(d))_ 💵**.

> % Return : r(d) = [ p(d) - p(d-1) ]  / [ p(d-1) ]

### State Classifications :
Classified the state (s(d)) based on percentage returns.
```
If          r(d) >= 0.1, s(d) = +1             (Bull state)
Else if    -0.1 < r(d) < 0.1, s(d) = 0         (Flat state)
Else        s(d) = -1                          (Bear state)
```

### Value Function :
Obtained V(N) based on the states classified.
```
If        s(d+1) = 1 & s(d) = 0   --->  V(d+1) = V(d) + 1
Else if   s(d+1) = -1 & s(d) = 0  --->  V(d+1) = V(d) - 1
Else      (in all other cases)    --->  V(d+1) = V(d)
```

## Transition distribution calculation:
Determining the probability distribution of transitioning from state _s(d)_ to different possible states using data up to day _d_.
* Used dictionary to keep track of the counts of transitions between states. The keys represent transitions from one state to another.
* Updated transition counts and probabilities as new data points arrive.
* Continuously calculated probabilities based on **streaming data**.

# RESULTS ✅

