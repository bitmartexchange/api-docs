# Cancel All Orders

Cancel orders for given condintions.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/orders?symbol=BMX_ETH&side=buy"

// timestamp is in milliseconds and the authorization header is "Bearer " + token
headers = {"X-BM-TIMESTAMP": xxx, "X-BM-AUTHORIZATION": "xxx"}

response = requests.delete(url, headers=headers)

print(response.text)
```

### Sample Response

```js
{}
```

#### Request Parameter

| Parameter | Type | Description |
| :--- | :--- | :--- |
| symbol | query | Trading pair symbol |
| side | query | 'buy' or 'sell' |







