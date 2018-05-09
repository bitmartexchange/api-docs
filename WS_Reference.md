# Bitmart WebSocket Reference

websocket URL https://ws.bitmart.com/

#### Heartbeat
REquest: {"subscribe":"ping"}
Response: {"subscribe":"pong"}


#### 1 Real-time trading info


```json
subscribe:
{"subscribe":"price", "symbol":12, "local": "zh_CN"}

broadcast:
{
  "subscribe":"price",
  "symbol": 12,
  "local": "zh_US",
  "data":{
    "o":"0.0000100",
    "h":"0.0000100",
    "l":"0.0000100",
    "v":"0.0000100",
    "c":"0.0000100",
    "increase":"1",
    "fluctuation":"-0.05",
    "rate":"0",
    "sign":"USD"
  }
}

cancel subscription:
{"subscribe":"price_cancel", "symbol":12}

```
##### Sub Parameters
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | topic: price, real-time price
|symbol       | trading pair id
|local    | language: zh_CN, en_US



##### Pub Values
| Filed | Description |
|:-------------:|:-------------|
|s | status: ok, no_data
|o | open price
|h | highest price
|l | lowest price
|v | volume
|c | close price
|increase | 1: increase 0: decrease 2: flat
|fluctuation | increase rate
|rate | corresponding fiat coin price
|sign | corresponding fiat coin unit






---------



#### 2 Real-time k-line info

```json
subscribe:
{"subscribe":"kline", "symbol":12, "step": 3}

broadcast:
{
  "subscribe":"kline",
  "symbol": 12,
  "step": 3,
  "data":{
    "o":"0.0000100",
    "h":"0.0000100",
    "l":"0.0000100",
    "v":"0.0000100",
    "c":"0.0000100",
    "t": 1231223121
  }
}

cancel subscription:
{"subscribe":"kline_cancel", "symbol":12, "step": 3}

```
##### Sub Parameters
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | subscription topic: kline
|symbol       | trading pair id
|step    | period, default: 1m

###### Parameters step Example
| key | value |
|:-------------:|:-------------|
|1  | 1 min |
|3  | 3 min |
|5  | 5 min |
|15 | 15 min |
|30 | 30 min |
|45 | 45 min |
|60 | 1 hr |
|120    | 2 hr |
|180    | 3 hr |
|240    | 4 hr |
|1d | 1 day |
|1w | 1 week |
|1m | 1 month |

##### Pub Values
| Filed | Description |
|:-------------:|:-------------|
|o | open price
|h | highest price
|l | lowest price
|v | volume
|c | close price
|t | timestamp, second









---------




#### 3 Real-time depth info

```json
subscription:
{"subscribe":"depth", "symbol":12, "percision": 8}

broadcast:
{
"subscribe":"depth",
"symbol":12,
"precision": 6,
"data":{
"sells":[{"amount":"0.001","total":"123.993","price":"1.09","count":"12","positions":"12"}],
"buys":[{"amount":"90.001","total":"923.993","price":"8.09","count":"14","positions":"32"}]
}
}

cancel subscription:
{"subscribe":"depth_cancel", "symbol":12, "percision": 8}

```
##### Sub Parameters
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | subscription topic: depth
|symbol       | trading pair id
|percision    | precision


##### Pub Values
| Filed | Description |
|:-------------:|:-------------|
|sells | sell
|buys | buy
|amount | amount
|price | price
|count | count





#### 4 Real-time Trading info

```json
subscription:
{"subscribe":"trade", "symbol":12, "precision": 8}

broadcast:
{
  "subscribe":"trade",
  "symbol":12,
  "percision": 6,
  "data":{
    "trades": [{isBuy: "0", amount: "0.000001", price: "0.0001000", time: 13333333}]
  }
}

cancel subscription:
{"subscribe":"trade_cancel", "symbol":12, "precision": 8}

```
##### Sub Parameters
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | subscription topic: trade
|symbol       | trading pair id
|percision    | precision


##### Pub Values
| Filed | Description |
|:-------------:|:-------------|
|amount| amount
|price | price
|isBuy| 0 buy, 1 sell 
|time| timestamp, second



