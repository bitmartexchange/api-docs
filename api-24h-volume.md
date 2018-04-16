API for 24h volume, You can only access the API one time every 60s

##### Request method

GET url: https://api.bitmart.com/api/v1/market_cap

##### Request parameter
NULL

##### 

##### Python sample
```Python
import requests
url = "https://api.bitmart.com/api/v1/market_cap"
response = requests.get(url)
content = response.content
print content

```

##### Return result sample

```json
{
  "BMX_ETH": {
    "priceChange": "-0.000005",
    "volume": "41645962.413491",  //24h volume denominated in BMX
    "marketName": "BMX_ETH",
    "lowPrice": "0.000076",
    "highPrice": "0.000097",
    "closeTime": 1523911632775,
    "id": 22,
    "baseVolume": "3538.39579772",  //24h volume denominated in ETH
    "openTime": 1523825232775,
    "priceChangePercent": "-6.097561",
    "lastPrice": "0.000077"
  },
  "MOBI_ETH": {
    "priceChange": "-0.000003",
    "volume": "472.8677",
    "marketName": "MOBI_ETH",
    "lowPrice": "0.000133",
    "highPrice": "0.000138",
    "closeTime": 1523911632786,
    "id": 24,
    "baseVolume": "0.0646678",
    "openTime": 1523825232786,
    "priceChangePercent": "-2.205882",
    "lastPrice": "0.000133"
  },
  "XLM_ETH": {
    "priceChange": "0.000007",
    "volume": "1377.84822",
    "marketName": "XLM_ETH",
    "lowPrice": "0.000549",
    "highPrice": "0.0006",
    "closeTime": 1523911632780,
    "id": 23,
    "baseVolume": "0.79392244",
    "openTime": 1523825232780,
    "priceChangePercent": "1.211073",
    "lastPrice": "0.000585"
  }
}
```




