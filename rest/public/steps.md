# Steps

Get a list of available steps (in minutes) that could be used to query k-line data.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/steps"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
[
   1,
   3,
   5,
   15,
   30,
   45,
   60,
   120,
   180,
   240,
   1440,
   10080,
   43200
]
```



