---
description: The handshake is used by clients to initiate a connection with the WebSocket.
---

# Connection Handshake

To initiate the handshake, the client connects to the WebSocket via the [Standard HTTP WebSocket Handshake](https://en.wikipedia.org/wiki/WebSocket#Protocol\_handshake).

After the standard handshake begins and the Upgrade has been completed, the **client is responsible for the initial handshake.**

Here's how that usually goes. The Client first starts with the `CLIENT_HELLO` packet.
