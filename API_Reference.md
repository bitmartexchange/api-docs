# API Reference

API URL https://api.bitmart.com/

#### 1 Trading Pairs


##### Example
```json
# Request
GET https://api.bitmart.com/tickers/market_cap

# Response
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

##### Request Parameters
NULL

##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|symbolId       | trading pair id
|website | trading pair address
|priceChange | price change within 24 hours
|high_24h | highest price within 24 hours
|low_24h |  lowest price within 24 hours
|new_24h |  latest price
|pair | trading pair name
|anchorId | target coin id
|anchorName | target coin name
|coinId | from coin id
|coinName | from coin name
|volume | trading volume
|baseVolume | target volume
|openTime | open time
|closeTime | close time





-----------






#### 2 Coin info


##### Example
```json
# Request
GET https://api.bitmart.com/tickers/coin

# Response
[
  {
  "coinName": "ETH",
  "coinId": 12,
  "website" : "https://www.bitmart.com/",
  "coinFullName": "Ethereum",
  }
]
```
##### Request Parameters
NULL

##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|coinId | coin id
|coinName | coin name
|coinFullName | coin full name








-----------






#### 3 Real-time trading pair info


##### Example
```json
# Request
GET https://api.bitmart.com/ticker/{pair}

# Response
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

##### Request Parameters
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|{pair} | trading pair, e.g.: BMX_ETH | Path |


##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|symbolId       | trading pair id
|website | trading pair website
|priceChange | price change within 24 hours
|high_24h | highest price within 24 hours
|low_24h |  lowest price within 24 hours
|new_24h |  latest price
|pair | trading pair name
|anchorId | target coin id
|anchorName | target coin name
|coinId | from coin id
|coinName | from coin name
|volume | trading volume
|baseVolume | target volume
|openTime | open time
|closeTime | close time








-----------






#### 4 k-line info


##### Example
```json
# Request
GET https://api.bitmart.com/market/kline?sourceTimeZone=GMT+08&symbol=22&step=15&from=1525760116&to=1525769116

# Response
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

##### Request Parameters
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | trading pair id | Query |
|from   | timestamp, second | Query |
|sourceTimeZone | timezone, e.g.: GMT+08 | Query |
|to | timestamp, second | Query |
|step | optional, default: 1m | Query |

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


##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|s | flag: 'ok', 'no_data'
|o | open price
|h | highest price
|l | lowest price
|v | volume
|c | close price
|t | timestamp, second







--------




#### 5 Depth info


##### Example
```json
# Request
GET https://api.bitmart.com/market/depth?symbol=2&precision=8

# Response
{
  "sells":[{"amount":"0.001","total":"123.993","price":"1.09","count":"12"}],
   "buys":[{"amount":"90.001","total":"923.993","price":"8.09","count":"14"}]
}
```
##### Request Parameters
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | trading pair id | Query |
|precision  | optional, default: 8 | Query |

##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|sells | trade type: sell
|buys | trade type: buy
|amount | amount
|total | total
|price | price
|count | count




--------





#### 6 查询某个交易对 成交 数据
##### Example
```json
# Request
GET https://api.bitmart.com/market/deal?symbol=2

# Response
[{
  "symbolName": "ETH/XLM",
  "amount": "0.001900",
  "createTime": 1523457226000,
  "count": "10.000000",
  "entrustType": 1,
  "price": "0.000190"
}]
```
##### Request Parameters
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | trading pair id | Query|

##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|symbolName | trading pair name
|amount| total amount = price * count
|price | price
|count | count
|entrustType| 0 buy，1 sell
|createTime| timestamp, second






--------






