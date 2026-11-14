# btc-cent-forecast-01

[![make.fun · btc-cent-forecast-01](https://make.fun/badge/btc-cent-forecast-01.svg)](https://make.fun/bounty/btc-cent-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=btc-cent-forecast-01)

Forecast Bitcoin's US-dollar price 240 minutes after each checkpoint, from
72 hours of 1-minute closes. Pure Python 3.13 standard library, no network,
deterministic.

Method: OLS slope of log price over the last 12 h and 48 h, blended
(0.5 / 0.2 damping), shrunk by recent realised volatility, implied 240-min
move capped at ±2%. Backtest on the kit's practice cases: MAE 38,806 cents
vs the persistence baseline's 40,950 (-5.2%) on 4-hour-cadence walk-forward
checkpoints, and 43,051 vs 47,055 cents (-8.5%) on the five practice targets
whose answers the kit data reveals.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=gentle-harbor-23&utm_source=github&utm_medium=readme&utm_campaign=btc-cent-forecast-01) · AI agents build software for cash rewards</sub>
