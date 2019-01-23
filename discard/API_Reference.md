# API Reference

API URL https://openapi.bitmart.com/

#### 1 Trading Pairs


##### Example
```json
# Request
GET https://openapi.bitmart.com/tickers/market_cap

# Response
[
   {
      "priceChange": "1.26%",
      "symbolId": 45,
      "website": "https://www.bitmart.com/trade?symbol=ABT_BTC",
      "depthEndPrecision": 8,
      "ask_1": "0.00006922",
      "anchorId": 2,
      "anchorName": "BTC",
      "pair": "ABT_BTC",
      "volume": "207961.00000000",
      "coinId": 24,
      "depthStartPrecision": 6,
      "high_24h": "0.00008922",
      "low_24h": "0.00005870",
      "new_24h": "0.00006854",
      "closeTime": 1531678097969,
      "bid_1": "0.00006800",
      "coinName": "ABT",
      "baseVolume": "13.44652201",
      "openTime": 1531591697969
   },
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
GET https://openapi.bitmart.com/tickers/coin

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
GET https://openapi.bitmart.com/ticker/{pair}

# Response
{
   "priceChange": "0.31%",
   "symbolId": 46,
   "website": "https://www.bitmart.com/trade?symbol=ABT_ETH",
   "depthEndPrecision": 6,
   "ask_1": "0.000974",
   "anchorId": 16,
   "anchorName": "ETH",
   "pair": "ABT_ETH",
   "volume": "163735.740000",
   "coinId": 24,
   "depthStartPrecision": 4,
   "high_24h": "0.001245",
   "low_24h": "0.000840",
   "new_24h": "0.000972",
   "closeTime": 1531678421082,
   "bid_1": "0.000965",
   "coinName": "ABT",
   "baseVolume": "151.491076",
   "openTime": 1531592021082
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
GET https://openapi.bitmart.com/market/kline?symbol=22&step=15&from=1525760116&to=1525769116

# Response
{  
    "c":[  
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000"
    ],
    "s":"ok",
    "t":[  
        1525761000,
        1525761900,
        1525763700,
        1525764600,
        1525765500,
        1525767300,
        1525768200,
        1525769100
    ],
    "v":[  
        "12684.07200000",
        "20.35020000",
        "0.00000000",
        "0.00000000",
        "0.00000000",
        "18.52880000",
        "0.00000000",
        "0.00000000"
    ],
    "h":[  
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000"
    ],
    "l":[  
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000"
    ],
    "o":[  
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000",
        "0.00007000"
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
GET https://openapi.bitmart.com/market/depth?symbol=22&precision=6

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
GET https://openapi.bitmart.com/market/deal?symbol=22

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






