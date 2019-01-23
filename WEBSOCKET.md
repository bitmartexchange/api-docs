# General

Real-time market data updates provide the fastest insight into order flow and trades. This however means that you are responsible for reading the message stream and using the message relevant for your needs which can include building real-time order books or tracking real-time trades.

### URL

```
wss://openws.bitmart.com
```

### Note

The websocket feed is publicly available, but connections to it are rate-limited to 1 per 4 seconds per IP.


### Protocol Overview

The websocket feed uses a bidirectional protocol, which encodes all messages as JSON objects.

**Error messages:** Most failure cases will cause an **error** message (a message with the field "message") to be emitted. This can be helpful for implementing a client or debugging issues.

### Subscribe

To begin receiving feed messages, you must first send a **subscribe** message to the server indicating which channels and products to receive. This message is mandatory — you will be disconnected if no **subscribe** has been received within 5 seconds.

Once a **subscribe** message is received, the server will respond with a subscription message along with the channel you are subscribed to.

A sample subscription message looks like:

```js
{
    "subscribe":"trade",
    "symbol":"BMX_ETH",
    "precision":6
}
```

Subsequent subscribe messages will add to the list of subscriptions. For example,

```js
{
    "subscribe":"trade",
    "precision":6,
    "symbol":"BMX_ETH",
    "data":{
        "trades":[
            {
                "side":"buy",
                "amount":"2.55882000",
                "price":"0.000110",
                "count":"23262.00",
                "time":1532018002502
            },
            ...
        ]
    }
}
```

If you want to unsubscribe from channel/product pair, send an **unsubscribe**. The structure is equvalent to **subscribe** messages.

Once **unsubscription** succeed, you will no longer receive subsequent **subscription** messages of the pair.

# Channel

* [Ping](websocket/ping.md)
* [Price](websocket/price.md)
* [K-line](websocket/kline.md)
* [Order Book](websocket/orders.md)
* [Trade History](websocket/trades.md)
