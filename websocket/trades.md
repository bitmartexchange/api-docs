# Trade History

Get the real-time information of the most recent trades for the given symbol.

### Sample Request \(Python\)

```py
# Feel free to use any websocket client you like. There are also online tools to test websocket.
# For example, here I use websocket-client. To install:
# sudo pip install websocket-client ()

import json
from websocket import create_connection

ws = create_connection("wss://openws.bitmart.com")

ws.send('{"subscribe":"trade","symbol":"BMX_ETH","precision":6}')

ws.recv()

ws.close()
```

### Sample Response

```js
{
    "subscribe":"trade",
    "precision":6,
    "symbol":"BMX_ETH",
    "data":{
        "trades":[
            {
                "side":"buy",
                "amount":"2.07827200",
                "price":"0.000112",
                "count":"18556.00",
                "time":1532039229703
            },
            {
                "side":"buy",
                "amount":"1.53126400",
                "price":"0.000112",
                "count":"13672.00",
                "time":1532039222810
            },
            {
                "side":"buy",
                "amount":"2.17190400",
                "price":"0.000112",
                "count":"19392.00",
                "time":1532039207104
            },
            {
                "side":"buy",
                "amount":"2.07468800",
                "price":"0.000112",
                "count":"18524.00",
                "time":1532039198301
            },
            {
                "side":"buy",
                "amount":"2.02137600",
                "price":"0.000112",
                "count":"18048.00",
                "time":1532039156202
            },
            {
                "side":"buy",
                "amount":"1.54582400",
                "price":"0.000112",
                "count":"13802.00",
                "time":1532039134822
            },
            {
                "side":"sell",
                "amount":"2.06169600",
                "price":"0.000112",
                "count":"18408.00",
                "time":1532039128018
            },
            {
                "side":"buy",
                "amount":"2.01152000",
                "price":"0.000112",
                "count":"17960.00",
                "time":1532039113315
            },
            {
                "side":"buy",
                "amount":"2.16854400",
                "price":"0.000112",
                "count":"19362.00",
                "time":1532039105701
            },
            {
                "side":"sell",
                "amount":"0.02563456",
                "price":"0.000112",
                "count":"228.88",
                "time":1532038517418
            },
            {
                "side":"sell",
                "amount":"0.15963248",
                "price":"0.000112",
                "count":"1425.29",
                "time":1532038487908
            },
            {
                "side":"sell",
                "amount":"0.15963248",
                "price":"0.000112",
                "count":"1425.29",
                "time":1532038483523
            },
            {
                "side":"sell",
                "amount":"0.14519120",
                "price":"0.000112",
                "count":"1296.35",
                "time":1532037923911
            },
            {
                "side":"buy",
                "amount":"0.04242672",
                "price":"0.000112",
                "count":"378.81",
                "time":1532037919821
            },
            {
                "side":"buy",
                "amount":"0.05924576",
                "price":"0.000112",
                "count":"528.98",
                "time":1532037919420
            }
        ]
    }
}
```

#### Request Parameter

| Parameter | Description |
| :--- | :--- |
| symbol| Trading pair symbol |
| precision | Price precision whose range is defined in symbol details |

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| amount | string | This is the number of coins offered at a specific price point. |
| order\_time | number | Order time (in milliseconds) |
| price | string | This is the offer price by a trader or traders at a specific price point. |
| count | string | This is the total number of orders traded at that that level. |
| type | String | Order type \("buy"/"sell"\) |



