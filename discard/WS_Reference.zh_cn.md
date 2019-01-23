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
  "local": "zh_CN",
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
{"subscribe":"price_cancel", "symbol":22, "local": "zh_CN"}

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
{"subscribe":"depth", "symbol":22, "precision": 6}

广播:
{  
  "subscribe":"depth",
  "symbol":22,
  "precision":6,
  "data":{  
    "buys":[  
      {  
        "amount":"13970.40",
        "total":"120000.000000",
        "price":"0.000128",
        "count":"3"
      },
      {  
        "amount":"19938.46",
        "total":"20000.000000",
        "price":"0.000127",
        "count":"2"
      },
      {  
        "amount":"10500.00",
        "total":"10000.000000",
        "price":"0.000126",
        "count":"2"
      },
      {  
        "amount":"12089.54",
        "total":"6608.340000",
        "price":"0.000125",
        "count":"2"
      },
      {  
        "amount":"20111.00",
        "total":"10000.000000",
        "price":"0.000124",
        "count":"3"
      },
      {  
        "amount":"24979.57",
        "total":"10000.000000",
        "price":"0.000123",
        "count":"5"
      },
      {  
        "amount":"12053.38",
        "total":"2000.000000",
        "price":"0.000122",
        "count":"3"
      },
      {  
        "amount":"30955.79",
        "total":"14199.280000",
        "price":"0.000121",
        "count":"4"
      },
      {  
        "amount":"102463.72",
        "total":"100000.000000",
        "price":"0.000120",
        "count":"11"
      },
      {  
        "amount":"10343.00",
        "total":"10000.000000",
        "price":"0.000119",
        "count":"4"
      },
      {  
        "amount":"10687.00",
        "total":"10000.000000",
        "price":"0.000118",
        "count":"3"
      },
      {  
        "amount":"18504.28",
        "total":"10000.000000",
        "price":"0.000117",
        "count":"2"
      },
      {  
        "amount":"11203.00",
        "total":"10000.000000",
        "price":"0.000116",
        "count":"2"
      },
      {  
        "amount":"33894.64",
        "total":"30000.000000",
        "price":"0.000115",
        "count":"8"
      },
      {  
        "amount":"11500.00",
        "total":"10000.000000",
        "price":"0.000114",
        "count":"3"
      },
      {  
        "amount":"15000.00",
        "total":"10000.000000",
        "price":"0.000113",
        "count":"2"
      },
      {  
        "amount":"10759.00",
        "total":"10000.000000",
        "price":"0.000112",
        "count":"5"
      },
      {  
        "amount":"10100.00",
        "total":"10000.000000",
        "price":"0.000111",
        "count":"2"
      },
      {  
        "amount":"9245.91",
        "total":"50000.000000",
        "price":"0.000110",
        "count":"8"
      },
      {  
        "amount":"118550.36",
        "total":"50000.000000",
        "price":"0.000109",
        "count":"4"
      },
      {  
        "amount":"20405.30",
        "total":"20000.000000",
        "price":"0.000108",
        "count":"3"
      },
      {  
        "amount":"10100.00",
        "total":"10000.000000",
        "price":"0.000107",
        "count":"2"
      },
      {  
        "amount":"10340.00",
        "total":"10000.000000",
        "price":"0.000106",
        "count":"2"
      },
      {  
        "amount":"12997.77",
        "total":"10000.000000",
        "price":"0.000105",
        "count":"6"
      },
      {  
        "amount":"6641.38",
        "total":"4821.000000",
        "price":"0.000103",
        "count":"2"
      },
      {  
        "amount":"4500.00",
        "total":"3000.000000",
        "price":"0.000102",
        "count":"2"
      },
      {  
        "amount":"5134.55",
        "total":"5134.550000",
        "price":"0.000101",
        "count":"1"
      },
      {  
        "amount":"351360.62",
        "total":"1306.400000",
        "price":"0.000100",
        "count":"14"
      },
      {  
        "amount":"1.20",
        "total":"1.200000",
        "price":"0.000099",
        "count":"1"
      }
    ],
    "sells":[  
      {  
        "amount":"629.47",
        "total":"629.470000",
        "price":"0.000130",
        "count":"1"
      },
      {  
        "amount":"12066.56",
        "total":"23007.560000",
        "price":"0.000131",
        "count":"1"
      },
      {  
        "amount":"14004.09",
        "total":"16875.000000",
        "price":"0.000132",
        "count":"4"
      },
      {  
        "amount":"10.00",
        "total":"10.000000",
        "price":"0.000133",
        "count":"1"
      },
      {  
        "amount":"150.00",
        "total":"75.000000",
        "price":"0.000134",
        "count":"2"
      },
      {  
        "amount":"2571.97",
        "total":"20.000000",
        "price":"0.000135",
        "count":"4"
      },
      {  
        "amount":"190.00",
        "total":"115.000000",
        "price":"0.000136",
        "count":"2"
      },
      {  
        "amount":"148.12",
        "total":"75.000000",
        "price":"0.000137",
        "count":"2"
      },
      {  
        "amount":"315.92",
        "total":"85.000000",
        "price":"0.000138",
        "count":"4"
      },
      {  
        "amount":"1685.00",
        "total":"1000.000000",
        "price":"0.000139",
        "count":"3"
      },
      {  
        "amount":"4021.21",
        "total":"5.000000",
        "price":"0.000140",
        "count":"7"
      },
      {  
        "amount":"160.00",
        "total":"75.000000",
        "price":"0.000141",
        "count":"2"
      },
      {  
        "amount":"75.00",
        "total":"75.000000",
        "price":"0.000143",
        "count":"1"
      },
      {  
        "amount":"1412.38",
        "total":"27.666600",
        "price":"0.000145",
        "count":"5"
      },
      {  
        "amount":"7700.00",
        "total":"7700.000000",
        "price":"0.000146",
        "count":"1"
      },
      {  
        "amount":"610.00",
        "total":"610.000000",
        "price":"0.000147",
        "count":"1"
      },
      {  
        "amount":"17349.66",
        "total":"75.000000",
        "price":"0.000148",
        "count":"3"
      },
      {  
        "amount":"12444.92",
        "total":"1000.000000",
        "price":"0.000149",
        "count":"8"
      },
      {  
        "amount":"141746.03",
        "total":"55.000000",
        "price":"0.000150",
        "count":"36"
      },
      {  
        "amount":"600.00",
        "total":"500.000000",
        "price":"0.000151",
        "count":"2"
      },
      {  
        "amount":"1500.00",
        "total":"1500.000000",
        "price":"0.000155",
        "count":"1"
      },
      {  
        "amount":"85.00",
        "total":"85.000000",
        "price":"0.000157",
        "count":"1"
      },
      {  
        "amount":"75.00",
        "total":"75.000000",
        "price":"0.000158",
        "count":"1"
      },
      {  
        "amount":"1375.00",
        "total":"1000.000000",
        "price":"0.000159",
        "count":"6"
      },
      {  
        "amount":"106.70",
        "total":"20.000000",
        "price":"0.000160",
        "count":"4"
      },
      {  
        "amount":"20.00",
        "total":"20.000000",
        "price":"0.000161",
        "count":"1"
      },
      {  
        "amount":"160.00",
        "total":"85.000000",
        "price":"0.000163",
        "count":"2"
      },
      {  
        "amount":"150.00",
        "total":"75.000000",
        "price":"0.000164",
        "count":"2"
      },
      {  
        "amount":"1650.00",
        "total":"1500.000000",
        "price":"0.000165",
        "count":"3"
      }
    ]
  }
}

取消订阅:
{"subscribe":"depth_cancel", "symbol":22, "percision": 6}

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
{"subscribe":"trade", "symbol":22, "precision": 6}

广播:
{  
  "subscribe":"trade",
  "symbol":22,
  "precision":6,
  "data":{  
    "trades":[  
      {  
        "isBuy":"0",
        "amount":"1.49111100",
        "price":"0.000129",
        "time":1527470105232
      },
      {  
        "isBuy":"1",
        "amount":"1.58063700",
        "price":"0.000129",
        "time":1527470092600
      },
      {  
        "isBuy":"1",
        "amount":"1.10720700",
        "price":"0.000129",
        "time":1527470074925
      },
      {  
        "isBuy":"0",
        "amount":"2.33090100",
        "price":"0.000129",
        "time":1527470056437
      },
      {  
        "isBuy":"0",
        "amount":"2.48350800",
        "price":"0.000129",
        "time":1527470036212
      },
      {  
        "isBuy":"1",
        "amount":"2.23028100",
        "price":"0.000129",
        "time":1527470000914
      },
      {  
        "isBuy":"0",
        "amount":"1.16745000",
        "price":"0.000129",
        "time":1527469966313
      },
      {  
        "isBuy":"0",
        "amount":"1.35081963",
        "price":"0.000129",
        "time":1527469958928
      },
      {  
        "isBuy":"0",
        "amount":"0.01916037",
        "price":"0.000129",
        "time":1527469958525
      },
      {  
        "isBuy":"0",
        "amount":"0.08120163",
        "price":"0.000129",
        "time":1527469954899
      },
      {  
        "isBuy":"0",
        "amount":"0.02489700",
        "price":"0.000129",
        "time":1527469920323
      },
      {  
        "isBuy":"0",
        "amount":"0.24703500",
        "price":"0.000129",
        "time":1527469919820
      },
      {  
        "isBuy":"1",
        "amount":"1.38352500",
        "price":"0.000129",
        "time":1527469876000
      },
      {  
        "isBuy":"1",
        "amount":"0.99084900",
        "price":"0.000129",
        "time":1527469853301
      },
      {  
        "isBuy":"1",
        "amount":"0.16383000",
        "price":"0.000129",
        "time":1527469852900
      }
    ]
  }
}

取消订阅:
{"subscribe":"trade_cancel", "symbol":22, "precision": 6}

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



