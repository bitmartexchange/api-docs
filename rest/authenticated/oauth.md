# Bearer Token

Get bearer token issued by the authorization server.

### HMAC SHA256 signature

HMAC SHA256 signature will be used as the value of _**client_secret**_ header.

Here is a step-by-step example of how to generate _**client_secret**_ from the Linux command line using ```echo```, ```openssl``` and ```curl```.

| Key | Value |
| :--- | :--- |
| API Key | 6591f7c2491db0a23a1d8ad6911c825e |
| API Secret | 8c08d9d5c3d15b105dbddaf96e427ac6 |
| memo | mymemo (memo is the name that user gave when the API was created, you can check the name by logging into bitmart.com and check API List under Account) |

```sh
[linux]$ echo -n "6591f7c2491db0a23a1d8ad6911c825e:8c08d9d5c3d15b105dbddaf96e427ac6:mymemo" | openssl dgst -sha256 -hmac "8c08d9d5c3d15b105dbddaf96e427ac6"
(stdin)= 18b9beb027d9ee75202655f37344ea5829c5c0d66a0781bf642bb3e944cf5019
```

### Sample Request \(Python\)

| Key | Value |
| :--- | :--- |
| grant_type | client_credentials |
| client_id | 6591f7c2491db0a23a1d8ad6911c825e |
| client_secret | 18b9beb027d9ee75202655f37344ea5829c5c0d66a0781bf642bb3e944cf5019 (HMAC SHA256 signed payload) |

```py
import requests
import json
import hmac
import hashlib

def create_sha256_signature(key, message): 
    return hmac.new(key, message, hashlib.sha256).hexdigest()

def get_access_token(api_key, api_secret, memo):
    url = "https://openapi.bitmart.com/v2/authentication"
    message = api_key + ':' + api_secret + ':' + memo
    data = {"grant_type": "client_credentials", "client_id": api_key, "client_secret": create_sha256_signature(api_secret, message)}
    response = requests.post(url, data = data)
    print(response.content)
    accessToken = response.json()['access_token']
    return accessToken

if __name__ == '__main__':
    access_token = get_access_token(api_key, client_secret, memo)
    print access_token

```


### Sample Response
```js
{
   "access_token":"m261aeb5bfa471c67c6ac41243959ae0dd408838cdc1a47e945305dd558e2fa78",
   "expires_in":900
}
```

#### Response Details

| Key | Type | Description |
| :--- | :--- | :--- |
| access_token | string | Bearer token |
| expires_in | numeric | Token expiration time (in seconds) |





