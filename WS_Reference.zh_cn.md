# BitMart WebSocket说明文档
采用订阅的模式

WebSocket URL wss://ws.bitmart.com/

#### 心跳

发送: {"subscribe":"ping"}

返回: {"subscribe":"pong"}


#### 1 交易对实时价格


```json
订阅:
{"subscribe":"price", "symbol":22, "local": "zh_CN"}

广播:
{
  "subscribe":"price",
  "symbol": 22,
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

取消订阅:
{"subscribe":"price_cancel", "symbol":22}

```
##### 参数
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | 订阅主题：price，实时价格
|symbol       | 交易对id
|local    | 语言：zh_CN，en_US



##### 返回值
| Filed | Description |
|:-------------:|:-------------|
|s | ok 有数据， no_data 没有数据
|o | 开盘价
|h | 最高价
|l | 最低价
|v | 交易数量
|c | 收盘价
|increase | 1涨0跌2平
|fluctuation | 涨幅，百分比需再*100
|rate | 对应法币金额
|sign | 对应法币单位






---------



#### 2 实时k线

```json
订阅:
{"subscribe":"kline", "symbol":22, "step": 3}

广播:
{
  "subscribe":"kline",
  "symbol": 22,
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

取消订阅:
{"subscribe":"kline_cancel", "symbol":22, "step": 3}

```
##### 返回值
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | 订阅主题：kline，实时k线数据
|symbol       | 交易对id
|step    | 周期，如: 1

###### 参数 step 取值
| key | value |
|:-------------:|:-------------|
|1  | 1分钟 |
|3  | 3分钟 |
|5  | 5分钟 |
|15 | 15分钟 |
|30 | 30分钟 |
|45 | 45分钟 |
|60 | 1小时 |
|120    | 2小时 |
|180    | 3小时 |
|240    | 4小时 |
|1d | 1天 |
|1w | 1周 |
|1m | 1月 |

##### 返回值
| Filed | Description |
|:-------------:|:-------------|
|o | 开盘价
|h | 最高价
|l | 最低价
|v | 交易数量
|c | 收盘价
|t | 精确到秒的时间戳









---------




#### 3 实时深度

```json
订阅:
{"subscribe":"depth", "symbol":22, "precision": 8}

广播:
{
"subscribe":"depth",
"symbol":22,
"precision": 6,
"data":{
"sells":[{"amount":"0.001","total":"123.993","price":"1.09","count":"12","positions":"12"}],
"buys":[{"amount":"90.001","total":"923.993","price":"8.09","count":"14","positions":"32"}]
}
}

取消订阅:
{"subscribe":"depth_cancel", "symbol":22, "percision": 8}

```
##### 参数
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | 订阅主题：depth，实时深度
|symbol       | 交易对id
|percision    | 精度


##### 返回值
| Filed | Description |
|:-------------:|:-------------|
|sells | 卖单
|buys | 买单
|amount | 数量
|price | 金额
|count | 委托单数量





#### 4 实时成交

```json
订阅:
{"subscribe":"trade", "symbol":22, "precision": 8}

广播:
{
  "subscribe":"trade",
  "symbol":22,
  "percision": 6,
  "data":{
    "trades": [{"isBuy": "0", "amount": "0.000001", "price": "0.0001000", "time": 13333333}]
  }
}

取消订阅:
{"subscribe":"trade_cancel", "symbol":22, "precision": 8}

```
##### 参数
| Parameters | Description |
|:-------------:|:-------------|
|subscribe    | 订阅主题：trade，实时成交
|symbol       | 交易对id
|percision    | 精度


##### 返回值
| Filed | Description |
|:-------------:|:-------------|
|amount| 金额
|price | 单价
|isBuy| 0买单，1卖单
|time| 精确到秒的时间戳



