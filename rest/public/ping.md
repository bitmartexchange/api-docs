# Ping

Test connectivity to the REST API.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/ping"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
{}
```



