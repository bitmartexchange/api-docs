# K-line

Get the real-time k-line data of a specific trading pair.

### Sample Request \(Python\)
```py
# Feel free to use any websocket client you like. There are also online tools to test websocket.
# For example, here I use websocket-client. To install:
# sudo pip install websocket-client ()

import json
from websocket import create_connection

ws = create_connection("wss://openws.bitmart.com")

ws.send('{"subscribe":"kline","symbol":"BMX_ETH","step":1}')

ws.recv()

ws.close()
```

### Sample Response

```js
{
    "subscribe":"kline",
    "symbol":"BMX_ETH",
    "step":"1",
    "data":{
        "open_price":"0.000112",
        "highest_price":"0.000112",
        "lowest_price":"0.000112",
        "volume":"0.000000",
        "current_price":"0.000112",
        "timestamp":1532033149669
    }
}
```

#### Request Parameter

| Parameter | Description |
| :--- | :--- |
| symbol | Trading pair symbol |
| step | [Steps](../rest/public/steps.md) of sampling \(in minutes, default 1 min\) |

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| current\_price | string | Current price |
| timestamp | numeric | Corrresponding timestamp \(in milliseconds\) |
| volume | string | Trading volume |
| highest\_price | string | Highest price |
| lowest\_price | string | Lowest price |
| open\_price | string | Open price |