# Trade History

Get a list of the most recent trades for the given symbol.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/symbols/BMX_ETH/trades"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
[  
   {
      "amount":"0.05768509",
      "order_time":1527057452000,
      "price":"0.004811",
      "count":"11.99",
      "type":"buy"
   },
   ...
]
```

#### Request Parameter

| Parameter | Type | Description |
| :--- | :--- | :--- |
| symbol | path | Trading pair symbol |

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| amount | string | This is the number of coins offered at a specific price point. |
| order\_time | number | Order time (in milliseconds) |
| price | string | This is the offer price by a trader or traders at a specific price point. |
| count | string | This is the total number of orders traded at that that level. |
| type | String | Order type \("buy"/"sell"\) |



