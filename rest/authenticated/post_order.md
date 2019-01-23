# Place a New Order

Create a new order.

### HMAC SHA256 signature

HMAC SHA256 signature will be used as the value of _**X-BM-SIGNATURE**_ header. We highly recommend to sign the payload in case the request body is hacked.

Here is a sample from the Linux command line request using ```echo```, ```openssl``` and ```curl```.

| Key | Value |
| :--- | :--- |
| symbol | BMX_ETH |
| side | buy |
| amount | 1 |
| price | 1 |

```sh
[linux]$ echo -n "amount=1&price=1&side=buy&symbol=BMX_ETH" | openssl dgst -sha256 -hmac "8c08d9d5c3d15b105dbddaf96e427ac6"
(stdin)= 2302088e474141fc7b498d0fa96c9cc2eda39a5a24fd1495d469d0a72e5fd483
```

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/orders"

// timestamp is in milliseconds and the authorization header is "Bearer " + token
// X-BM-SIGNATURE is the HMAC SHA256 signature of the request parameters encrypted by API Secret
headers = {"X-BM-TIMESTAMP": xxx, "X-BM-AUTHORIZATION": "xxx", "X-BM-SIGNATURE": "df658d1d61537a842dba5ddb3f69a96f04a87ba4a9b3fba478cece39cb5da57f", "Content-Type": "application/json"}

data = {"symbol": "BMX_ETH","amount": 1,"price" : 1,"side" : "buy"}

data = json.dumps(data)

response = requests.post(url, data=data, headers=headers)

print(response.text)
```

### Sample Request

```js
{
   "symbol":"BMX_ETH",
   "amount":1,
   "price":1,
   "side":"buy"
}
```

### Sample Response
```js
{
   "entrust_id":1223181
}
```

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| entrust_id | string | Order id |





