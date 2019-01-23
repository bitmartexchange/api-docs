# Ping

Test connectivity to the websocket feed.

### Sample Request \(Python\)

```py
# Feel free to use any websocket client you like. Here I use websocket-client. To install:
# sudo pip install websocket-client

import json
from websocket import create_connection

ws = create_connection("wss://openws.bitmart.com")

ws.send('{"subscribe":"ping"}')

ws.recv()

ws.close()
```

### Sample Response

```js
{"subscribe":"pong"}
```
