# Order Book

Get the real-time order details.

### Sample Request \(Python\)

```py
# Feel free to use any websocket client you like. There are also online tools to test websocket.
# For example, here I use websocket-client. To install:
# sudo pip install websocket-client ()

import json
from websocket import create_connection

ws = create_connection("wss://openws.bitmart.com")

ws.send('{"subscribe":"order","symbol":"BMX_ETH","precision":6}')

ws.recv()

ws.close()
```

### Sample Response

```js
{
    "subscribe":"depth",
    "symbol":"BMX_ETH",
    "precision":6,
    "data":{
        "buys":[
            {
                "amount":"30657.00",
                "total":"30657.00",
                "price":"0.000111",
                "count":"1"
            },
            {
                "amount":"53266.60",
                "total":"83923.60",
                "price":"0.000110",
                "count":"3"
            },
            {
                "amount":"41565.65",
                "total":"125489.25",
                "price":"0.000109",
                "count":"4"
            },
            {
                "amount":"25988.15",
                "total":"151477.40",
                "price":"0.000108",
                "count":"6"
            },
            {
                "amount":"25035.94",
                "total":"176513.34",
                "price":"0.000107",
                "count":"3"
            },
            {
                "amount":"27793.61",
                "total":"204306.95",
                "price":"0.000106",
                "count":"6"
            },
            {
                "amount":"64108.77",
                "total":"268415.72",
                "price":"0.000105",
                "count":"11"
            },
            {
                "amount":"589004.64",
                "total":"857420.36",
                "price":"0.000104",
                "count":"6"
            },
            {
                "amount":"131389.03",
                "total":"988809.39",
                "price":"0.000103",
                "count":"10"
            },
            {
                "amount":"18539.58",
                "total":"1007348.97",
                "price":"0.000102",
                "count":"4"
            },
            {
                "amount":"53118.54",
                "total":"1060467.51",
                "price":"0.000101",
                "count":"6"
            },
            {
                "amount":"95122.48",
                "total":"1155589.99",
                "price":"0.000100",
                "count":"13"
            },
            {
                "amount":"45311.42",
                "total":"1200901.41",
                "price":"0.000099",
                "count":"4"
            },
            {
                "amount":"24245.14",
                "total":"1225146.55",
                "price":"0.000098",
                "count":"3"
            },
            {
                "amount":"167032.04",
                "total":"1392178.59",
                "price":"0.000097",
                "count":"3"
            },
            {
                "amount":"34388.33",
                "total":"1426566.92",
                "price":"0.000096",
                "count":"5"
            },
            {
                "amount":"6120.15",
                "total":"1432687.07",
                "price":"0.000095",
                "count":"5"
            },
            {
                "amount":"52000.00",
                "total":"1484687.07",
                "price":"0.000094",
                "count":"3"
            },
            {
                "amount":"64223.21",
                "total":"1548910.28",
                "price":"0.000093",
                "count":"2"
            },
            {
                "amount":"66343.53",
                "total":"1615253.81",
                "price":"0.000092",
                "count":"4"
            }
        ],
        "sells":[
            {
                "amount":"7734.95",
                "total":"7734.95",
                "price":"0.000113",
                "count":"3"
            },
            {
                "amount":"8110.00",
                "total":"15844.95",
                "price":"0.000114",
                "count":"4"
            },
            {
                "amount":"31660.27",
                "total":"47505.22",
                "price":"0.000115",
                "count":"6"
            },
            {
                "amount":"22107.00",
                "total":"69612.22",
                "price":"0.000116",
                "count":"2"
            },
            {
                "amount":"11382.69",
                "total":"80994.91",
                "price":"0.000117",
                "count":"4"
            },
            {
                "amount":"13523.00",
                "total":"94517.91",
                "price":"0.000118",
                "count":"8"
            },
            {
                "amount":"22897.44",
                "total":"117415.35",
                "price":"0.000119",
                "count":"7"
            },
            {
                "amount":"40973.15",
                "total":"158388.50",
                "price":"0.000120",
                "count":"12"
            },
            {
                "amount":"36744.30",
                "total":"195132.80",
                "price":"0.000121",
                "count":"9"
            },
            {
                "amount":"81796.73",
                "total":"276929.53",
                "price":"0.000122",
                "count":"5"
            },
            {
                "amount":"60000.00",
                "total":"336929.53",
                "price":"0.000123",
                "count":"2"
            },
            {
                "amount":"40429.96",
                "total":"377359.49",
                "price":"0.000124",
                "count":"3"
            },
            {
                "amount":"42656.66",
                "total":"420016.15",
                "price":"0.000125",
                "count":"8"
            },
            {
                "amount":"130782.16",
                "total":"550798.31",
                "price":"0.000126",
                "count":"3"
            },
            {
                "amount":"226198.12",
                "total":"776996.43",
                "price":"0.000127",
                "count":"5"
            },
            {
                "amount":"440014.87",
                "total":"1217011.30",
                "price":"0.000128",
                "count":"3"
            },
            {
                "amount":"5903.72",
                "total":"1222915.02",
                "price":"0.000129",
                "count":"1"
            },
            {
                "amount":"100.00",
                "total":"1223015.02",
                "price":"0.000130",
                "count":"1"
            },
            {
                "amount":"34947.00",
                "total":"1257962.02",
                "price":"0.000132",
                "count":"1"
            },
            {
                "amount":"50000.00",
                "total":"1307962.02",
                "price":"0.000133",
                "count":"1"
            }
        ]
    }
}
```

#### Request Parameters

| Parameter | Description |
| :--- | :--- |
| symbol | Trading pair symbol |
| precision | Price precision whose range is defined in symbol details |

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| amount | string | This is the number of coins offered at a specific price point. |
| total | string | This is the cumulation number of coins that offered to a specific price point. |
| price | string | This is the offer price by a trader or traders at a specific price point. |
| count | string | This is the total number of orders at that level. |
| buys | array | Array of 'buy' type orders |
| sells | array | Array of 'sell' type orders |



