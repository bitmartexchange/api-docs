# Price

Get the real-time price information of a trading pair.

### Sample Request \(Python\)

```py
# Feel free to use any websocket client you like. There are also online tools to test websocket.
# For example, here I use websocket-client. To install:
# sudo pip install websocket-client ()

import json
from websocket import create_connection

ws = create_connection("wss://openws.bitmart.com")

ws.send('{"subscribe":"price","symbol":"BMX_ETH"}')

ws.recv()

ws.close()
```

### Sample Response

```js
{
    "subscribe":"price",
    "symbol":"BMX_ETH",
    "data":{
        "open_price":"0.000109",
        "highest_price":"0.000122",
        "lowest_price":"0.000094",
        "volume":"2396.650514",
        "current_price":"0.000112",
        "fluctuation":"+0.0275",
        "rate":"0.05 USD",
        "timestamp":1532033149669
    }
}
```

#### Request Parameter

| Parameter | Description |
| :--- | :--- |
| symbol | Trading pair symbol |

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| current\_price | string | Current price |
| timestamp | numeric | Corrresponding timestamp \(in milliseconds\) |
| volume | string | Trading volume |
| highest\_price | string | Highest price within 24 hr |
| lowest\_price | string | Lowest price within 24 hr |
| open\_price | string | Open price |
| fluctuation | string | Price change within 24 hr |
| rate | string | Price of the base coin |
