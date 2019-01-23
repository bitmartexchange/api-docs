# K-line

Get the k-line data of a specific trading pair.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/symbols/BMX_ETH/kline?step=15&from=1525760116000&to=1525769116000"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
[  
    {  
        "timestamp":1525761000000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    },
    {  
        "timestamp":1525761900000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    },
    {  
        "timestamp":1525763700000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    },
    {  
        "timestamp":1525764600000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    },
    {  
        "timestamp":1525765500000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    },
    {  
        "timestamp":1525767300000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    },
    {  
        "timestamp":1525768200000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    },
    {  
        "timestamp":1525769100000,
        "open_price":"0.010130",
        "highest_price":"0.010130",
        "lowest_price":"0.010130",
        "current_price":"0.010130",
        "volume":"0.000000"
    }
]
```

#### Request Parameters

| Parameter | Type | Description |
| :--- | :--- | :--- |
| symbol | path | Trading pair symbol |
| from | query | Start time of k-line data \(in milliseconds\) |
| to | query | End time of k-line data \(in milliseconds\) |
| step | query | [Steps](steps.md) of sampling \(in minutes, default 1 min\) |

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| data | array | Response data |
| current_price | string | Current price |
| timestamp | numeric | Corrresponding timestamp \(in milliseconds\) |
| volume | string | Trading volume |
| highest_price | string | Highest price |
| lowest_price | string | Lowest price |
| open_price | string | Open price |



