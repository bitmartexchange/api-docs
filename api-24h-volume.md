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

##### Return Result

```json
{
	"BMX_ETH": {
		"priceChange":"-0.000002",
		"volume":"28977076.7691",
		"marketName":"BMX_ETH",
		"lowPrice":"0.000056",
		"highPrice":"0.000064",
		"closeTime":1523644015182,
		"id":22,
		"baseVolume":"1757.8032367",
		"openTime":1523557615182,
		"priceChangePercent":"-3.225806",
		"lastPrice":"0.00006"
	},
	"MOBI_ETH": {
		"priceChange":"0.000021",
		"volume":"2068.7943",
		"marketName":"MOBI_ETH",
		"lowPrice":"0.0001",
		"highPrice":"0.00015",
		"closeTime":1523644015193,
		"id":24,
		"baseVolume":"0.2730309",
		"openTime":1523557615193,
		"priceChangePercent":"18.75",
		"lastPrice":"0.000133"
	},
	"XLM_ETH": {
		"priceChange":"0.00002",
		"volume":"2139.0326",
		"marketName":"XLM_ETH",
		"lowPrice":"0.00049",
		"highPrice":"0.00058",
		"closeTime":1523644015187,
		"id":23,
		"baseVolume":"1.1272803",
		"openTime":1523557615187,
		"priceChangePercent":"3.636364",
		"lastPrice":"0.00057"
	}
}
```




