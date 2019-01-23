# Currencies

Get a list of available currencies.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/currencies"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
[
   {
      "id":"ETH",
      "name":"Ethereum",
      "withdraw_enabled":true,
      "deposit_enabled":true
   },
   ...
]
```



