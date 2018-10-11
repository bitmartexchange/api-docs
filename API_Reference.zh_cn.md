# Bitmart API 说明文档

API URL https://openapi.bitmart.com/

#### 1 查询所有交易对


##### 请求样例
```json
# 请求
GET https://openapi.bitmart.com/tickers/market_cap

# 响应
[
   {
      "priceChange":"4.21%",
      "symbolId":45,
      "website":"https://www.bitmart.com/trade.html?symbol=45",
      "ask_1":"0.00013000",
      "anchorId":2,
      "anchorName":"BTC",
      "pair":"ABT_BTC",
      "volume":"23383.38200980",
      "coinId":24,
      "high_24h":"0.00013090",
      "low_24h":"0.00012000",
      "new_24h":"0.00012827",
      "closeTime":1526539974569,
      "bid_1":"0.00012810",
      "coinName":"ABT",
      "baseVolume":"2.91795127",
      "openTime":1526453574569,
      "depthStartPrecision":4,
      "depthEndPrecision":6
   }
]
```

##### 请求参数
NULL

##### 返回值
| Field | Description |
|:-------------:|:-------------|
|symbolId       | 交易对id
|url | 交易对地址
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
|ask_1 | 卖一价
|bid_1 | 买一价
|depthStartPrecision | 最小深度精度
|depthEndPrecision | 最大深度精度



-----------






#### 2 查询所有虚拟币信息


##### 请求样例
```json
# 请求
GET https://openapi.bitmart.com/tickers/coin

# 响应
[
   {
      "coinName":"ETH",
      "coinId":16,
      "coinFullName":"Ethereum"
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
GET https://openapi.bitmart.com/ticker/{pair}

# 响应
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

##### 请求参数
| Parameters | Description | Type
|:-------------:|:-------------:|:-------------|
|{pair} | 交易对,如: BMX_ETH | Path |


##### 返回值
| Field | Description |
|:-------------:|:-------------|
|symbolId       | 交易对id
|url | 交易对地址
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
|ask_1 | 卖一价
|bid_1 | 买一价
|depthStartPrecision | 最小深度精度
|depthEndPrecision | 最大深度精度







-----------






#### 4 查询某个交易对 kline 数据


##### 请求样例
```json
# 请求
GET https://openapi.bitmart.com/market/kline?symbol=22&step=15&from=1525760116&to=1525769116

# 响应
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

##### 请求参数
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | 交易対类型id | Query |
|from   | 开始时间的时间戳,精确到秒 | Query |
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
GET https://openapi.bitmart.com/market/depth?symbol=22&precision=6

# 响应
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
##### 请求参数
| Parameters | Description | Type
|:-------------:|:-------------:|:-------------|
|symbol | 交易対类型id | Query
|precision  | 精度 | Query |

##### 返回值
| Field | Description |
|:-------------:|:-------------|
|sells | 卖单
|buys | 买单
|amount | 数量
|price | 金额
|total | 总交易金额
|count | 委托单数量




--------





#### 6 查询某个交易对最近20条成交数据
##### 请求样例
```json
# 请求
GET https://openapi.bitmart.com/market/deal?symbol=22

# 响应
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
##### 请求参数
| Parameters | Description | Type |
|:-------------:|:-------------:|:-------------|
|symbol | 交易対类型id | Query |

##### 返回值
| Field | Description |
|:-------------:|:-------------|
|amount| 金额
|count| 数量
|price | 单价
|entrustType| 0买单，1卖单
|createTime| 精确到秒的时间戳






--------






