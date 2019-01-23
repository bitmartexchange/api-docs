# Time

Test connectivity to the REST API and get the current server time (in milliseconds).

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/time"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
{
   "server_time": 1527777538000
}
```



