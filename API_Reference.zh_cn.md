# Bitmart API 说明文档 

API URL https://api.bitmart.com/

#### 1 查询所有交易对


##### 请求样例
```json
# 请求
GET https://api.bitmart.com/tickers/market_cap

# 响应
[{
  "priceChange": "0%",
  "symbolId": 20,
  "website": "https://www.bitmart.com/trade.html?symbol=22",
  "high_24h": "0.004000",
  "low_24h": "0.004000",
  "new_24h": "0.004000",
  "pair": "BMX_ETH",
  "anchorId": 16,
  "anchorName": "ETH",
  "coinId": 18,
  "coinName": "BMX",
  "volume": "249.986378",
  "baseVolume": "1.114146",
  "openTime": 1524105824549,
  "closeTime": 1524192224549
}]
```

##### 请求参数
NULL

##### 返回值
| Field | Description |
|:-------------:|:-------------|
|symbolId       | 交易对id
|website | 交易对地址
|priceChange | 24小时涨幅百分比
|high_24h | 24小时最高价格
|low_24h |  24小时最低价格
|new_24h |  24小时最新价格
|pair | 交易对
|anchorId | 锚定虚拟币id
|anchorName | 锚定虚拟币名
|coinId | 交易虚拟币id
|coinName | 交易虚拟币名
|volume | 交易虚拟币数量
|baseVolume | 锚定虚拟币数量
|openTime | 开盘时间
|closeTime | 收盘时间





-----------






#### 2 查询所有虚拟币信息


##### 请求样例
```json
# 请求
GET https://api.bitmart.com/tickers/coin

# 响应
[
  {
  "coinName": "ETH",
  "coinId": 12,
  "website" : "https://www.bitmart.com/",
  "coinFullName": "Ethereum",
  }
]
```
##### 请求参数
NULL

##### 返回值
| Field | Description |
|:-------------:|:-------------|
|coinId | 交易虚拟币id
|coinName | 交易虚拟币名
|coinFullName | 交易虚拟币全称








-----------






#### 3 查询某个交易对实时信息


##### 请求样例
```json
# 请求
GET https://api.bitmart.com/ticker/{pair}

# 响应
{
  "priceChange": "0%",
  "symbolId": 20,
  "website": "https://www.bitmart.com/trade.html?symbol=22",
  "high_24h": "0.004000",
  "low_24h": "0.004000",
  "new_24h": "0.004000",
  "pair": "BMX_ETH",
  "anchorId": 16,
  "anchorName": "ETH",
  "coinId": 18,
  "coinName": "BMX",
  "volume": "249.986378",
  "baseVolume": "1.114146",
  "openTime": 1524105824549,
  "closeTime": 1524192224549
}
```

##### 请求参数
| Parameters | Description | Type
|:-------------:|:-------------:|:-------------|
|{pair} | 交易对,如: BMX_ETH | Path |


##### 返回值
| Field | Description |
|:-------------:|:-------------|
|symbolId       | 交易对id
|website | 交易对地址
|priceChange | 24小时涨幅百分比
|high_24h | 24小时最高价格
|low_24h |  24小时最低价格
|new_24h |  24小时最新价格
|pair | 交易对
|anchorId | 锚定虚拟币id
|anchorName | 锚定虚拟币名
|coinId | 交易虚拟币id
|coinName | 交易虚拟币名
|volume | 交易虚拟币数量
|baseVolume | 锚定虚拟币数量
|openTime | 开盘时间
|closeTime | 收盘时间








-----------






#### 4 查询某个交易对 kline 数据


##### 请求样例
```json
# 请求
GET https://api.bitmart.com/market/kline?sourceTimeZone=GMT+08&symbol=22&step=15&from=1525760116&to=1525769116

# 响应
{
  "c": [
    177,
    177.04,
    177.22,
    177.11,
    171.11
  ],
  "s": "ok",
  "t": [
    1516579200,
    1516665600,
    1516752000,
    1516838400,
    1516924800
  ],
  "v": [
    26023622,
    26523681,
    26622200,
    26722213,
    36722213
  ],
  "h": [
    177.78,
    177.18,
    176.78,
    176.38,
    176.18
  ],
  "l": [
    176.6016,
    175.6016,
    174.6016,
    173.6016,
    171.6016
  ],
  "o": [
    177.3,
    177.3,
    177.25,
    177.25,
    177.35
  ]
}
```

##### 请求参数
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | 交易対类型id | Query |
|from   | 开始时间的时间戳,精确到秒 | Query |
|sourceTimeZone | 时区，如：北京时间, GMT+08 | Query |
|to | 结束时间的时间戳,精确到秒 | Query |
|step | 周期 | Query |

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
| Field | Description |
|:-------------:|:-------------|
|s | ok 有数据， no_data 没有数据
|o | 开盘价
|h | 最高价
|l | 最低价
|v | 交易数量
|c | 收盘价
|t | 精确到秒的时间戳







--------




#### 5 查询某个交易对 深度 数据


##### 请求样例
```json
# 请求
GET https://api.bitmart.com/market/depth?symbol=2&precision=8

# 响应
{
  "sells":[{"amount":"0.001","total":"123.993","price":"1.09","count":"12"}],
   "buys":[{"amount":"90.001","total":"923.993","price":"8.09","count":"14"}]
}
```
##### 请求参数
| Parameters | Description | Type
|:-------------:|:-------------:|:-------------|
|symbol | 交易対类型id | Query
|precision  | 精度，默认：8 | Query |

##### 返回值
| Field | Description |
|:-------------:|:-------------|
|sells | 卖单
|buys | 买单
|amount | 数量
|price | 金额
|count | 委托单数量




--------





#### 6 查询某个交易对 成交 数据
##### 请求样例
```json
# 请求
GET https://api.bitmart.com/market/deal?symbol=2

# 响应
[{
  "symbolName": "ETH/XLM",
  "amount": "0.001900",
  "createTime": 1523457226000,
  "count": "10.000000",
  "entrustType": 1,
  "price": "0.000190"
}]
```
##### 请求参数
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | 交易対类型id | Query |

##### 返回值
| Field | Description |
|:-------------:|:-------------|
|symbolName |交易对的名称
|amount| 金额
|price | 单价
|count | 数量
|entrustType| 0买单，1卖单
|createTime| 精确到秒的时间戳






--------






