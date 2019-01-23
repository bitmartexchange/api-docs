# Wallet Balances

Get user wallet balances.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/wallet"

// timestamp is in milliseconds and the authorization header is "Bearer " + token
headers = {"X-BM-TIMESTAMP": xxx, "X-BM-AUTHORIZATION": "Bearer xxxx-here-is-the-access-token"}

response = requests.get(url, headers=headers)

print(response.text)
```

### Sample Response

```js
[
   {
        "id": "BTC"
        "available": 10,
        "name": "Bitcoin",
        "frozen": 0,
    }, 
    
    ...
]
```

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| id | string | This is the short name of the currency. |
| name | string | This is the full name of the currency. |
| available | string | This is the amount of available currency. |
| frozen | string | This is the amount of frozen currency. |




