# Symbols

Get a list of symbol names.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/symbols"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
[  
   "BMX_ETH",
   "XLM_ETH",
   "MOBI_ETH",
   ...
]
```



