# API Reference

API URL https://api.bitmart.com/

#### 1 Trading Pairs


##### Example
```json
# Request
GET https://api.bitmart.com/tickers/market_cap

# Response
[
  {
    priceChange: "4.21%",
    symbolId: 45,
    website: "https://www.bitmart.com/trade.html?symbol=45",
    ask_1: "0.00013000",
    anchorId: 2,
    anchorName: "BTC",
    pair: "ABT_BTC",
    volume: "23383.38200980",
    coinId: 24,
    high_24h: "0.00013090",
    low_24h: "0.00012000",
    new_24h: "0.00012827",
    closeTime: 1526539974569,
    bid_1: "0.00012810",
    coinName: "ABT",
    baseVolume: "2.91795127",
    openTime: 1526453574569,
    depthStartPrecision: 4,
    depthEndPrecision: 6
  }
]
```

##### Request Parameters
NULL

##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|symbolId       | trading pair id
|url | trading pair address
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
|ask_1 | asked price
|bit_1 | bid price
|depthStartPrecision | start precision for depth
|depthEndPrecision | end precision for depth




-----------






#### 2 Coin info


##### Example
```json
# Request
GET https://api.bitmart.com/tickers/coin

# Response
[
   {
      "coinName":"ETH",
      "coinId":16,
      "coinFullName":"Ethereum"
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
   "priceChange":"0%",
   "symbolId":22,
   "ask_1":"0.004811",
   "anchorId":16,
   "anchorName":"ETH",
   "pair":"BMX_ETH",
   "url":"https://www.bitmart.com/trade.html?symbol=22",
   "volume":"560356.868000",
   "coinId":18,
   "high_24h":"0.004811",
   "low_24h":"0.004811",
   "new_24h":"0.004811",
   "closeTime":1526047727412,
   "bid_1":"0.004811",
   "coinName":"BMX",
   "baseVolume":"2542.024679",
   "openTime":1525961327412,
   "depthStartPrecision": 4,
   "depthEndPrecision": 6
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
|url | trading pair url
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
|ask_1 | asked price
|bit_1 | bid price
|depthStartPrecision | start precision for depth
|depthEndPrecision | end precision for depth







-----------






#### 4 k-line info


##### Example
```json
# Request
GET https://api.bitmart.com/market/kline?symbol=22&step=15&from=1525760116&to=1525769116

# Response
{
   "c":[
      177,
      177.04,
      177.22,
      177.11,
      171.11
   ],
   "s":"ok",
   "t":[
      1516579200,
      1516665600,
      1516752000,
      1516838400,
      1516924800
   ],
   "v":[
      26023622,
      26523681,
      26622200,
      26722213,
      36722213
   ],
   "h":[
      177.78,
      177.18,
      176.78,
      176.38,
      176.18
   ],
   "l":[
      176.6016,
      175.6016,
      174.6016,
      173.6016,
      171.6016
   ],
   "o":[
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
GET https://api.bitmart.com/market/depth?symbol=22&precision=6

# Response
{
   "buys":[
      {
         "amount":"12.09",
         "total":"14835.90",
         "price":"0.01013000",
         "count":"5"
      },
      {
         "amount":"0.07",
         "total":"0.07",
         "price":"0.00600000",
         "count":"1"
      },
      {
         "amount":"80.00",
         "total":"40.00",
         "price":"0.00101300",
         "count":"2"
      },
      {
         "amount":"0.07",
         "total":"0.07",
         "price":"0.00000800",
         "count":"1"
      },
      {
         "amount":"1.00",
         "total":"1.00",
         "price":"0.00000100",
         "count":"1"
      }
   ],
   "sells":[
      {
         "amount":"1.00",
         "total":"1.00",
         "price":"0.87531000",
         "count":"1"
      },
      {
         "amount":"20.00",
         "total":"20.00",
         "price":"0.90000000",
         "count":"1"
      },
      {
         "amount":"50.00",
         "total":"50.00",
         "price":"0.91000000",
         "count":"1"
      }
   ]
}
```
##### Request Parameters
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | trading pair id | Query |
|precision  | optional | Query |

##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|sells | trade type: sell
|buys | trade type: buy
|amount | amount
|price | price
|total | total
|count | count




--------





#### 6 Latest 20 deals
##### Example
```json
# Request
GET https://api.bitmart.com/market/deal?symbol=22

# Response
[
   {
      "amount":"0.001900",
      "count":"120",
      "createTime":1526539240000,
      "entrustType":1,
      "price":"0.000190"
   }
]
```
##### Request Parameters
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | trading pair id | Query|

##### Return Values
| Filed | Description |
|:-------------:|:-------------|
|amount| total amount = price * count
|count|count
|price | price
|entrustType| 0 buy，1 sell
|createTime| timestamp, second






--------






