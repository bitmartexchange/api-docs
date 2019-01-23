# Order Book

Get the full order book.

### Sample Request \(Python\)

```py
import requests

url = "https://openapi.bitmart.com/v2/symbols/BMX_ETH/orders?precision=6"

response = requests.request("GET", url)

print(response.text)
```

### Sample Response

```js
{  
   "buys":[
      {
         "amount":"4800.00",
         "total":"4800.00",
         "price":"0.000767",
         "count":"1"
      },
      {
         "amount":"99996475.79",
         "total":"100001275.79",
         "price":"0.000201",
         "count":"1"
      },
      {
         "amount":"68.00",
         "total":"100001343.79",
         "price":"0.000102",
         "count":"1"
      },
      {
         "amount":"165.00",
         "total":"100001508.79",
         "price":"0.000053",
         "count":"3"
      },
      {
         "amount":"55.00",
         "total":"100001563.79",
         "price":"0.000028",
         "count":"1"
      },
      {
         "amount":"50.00",
         "total":"100001613.79",
         "price":"0.000020",
         "count":"1"
      },
      {
         "amount":"0.05",
         "total":"100001613.84",
         "price":"0.000019",
         "count":"1"
      },
      {
         "amount":"5019.97",
         "total":"100006633.81",
         "price":"0.000010",
         "count":"2"
      }
   ],
   "sells":[
      {
         "amount":"100.00",
         "total":"100.00",
         "price":"0.007000",
         "count":"1"
      },
      {
         "amount":"6997.00",
         "total":"7097.00",
         "price":"1.000000",
         "count":"1"
      },
      {
         "amount":"0.01",
         "total":"7097.01",
         "price":"1.000003",
         "count":"1"
      }
   ]
}
```

#### Request Parameters

| Parameter | Type | Description |
| :--- | :--- | :--- |
| symbol | path | Trading pair symbol |
| precision | query | Price precision whose range is defined in symbol details |

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| amount | string | This is the number of coins offered at a specific price point. |
| total | string | This is the cumulation number of coins that offered to a specific price point. |
| price | string | This is the offer price by a trader or traders at a specific price point. |
| count | string | This is the total number of orders at that level. |
| buys | array | Array of 'buy' type orders |
| sells | array | Array of 'sell' type orders |



