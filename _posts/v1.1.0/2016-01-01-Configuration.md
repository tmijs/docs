---
layout: post
title: "Configuration"
date: 2016-01-01 00:00:00 -0400
categories: v1.1.0
---
# Configuration

Each and every option listed below is optional. Running tmi.js without options will result as an anonymous connection to Twitch and you will have to join the channels manually.

``options``: (_Optional_)

- ``debug``: _Boolean_ - Show debug messages in console (Default: ``false``)

``connection``: (_Optional_)

- ``server``: _String_ - Connect to this server (_Overrides cluster and connect to this server instead_)
- ``port``: _Integer_ - Connect on this port (Default: ``80``)
- ``reconnect``: _Boolean_ - Reconnect to Twitch when disconnected from server (Default: ``false``)
- ``maxReconnectAttempts``: _Integer_ - Max number of reconnection attempts (Default: ``Infinity``)
- ``maxReconnectInterval``: _Integer_ - Max number of ms to delay a reconnection (Default: ``30000``)
- ``reconnectDecay``: _Integer_ - The rate of increase of the reconnect delay (Default: ``1.5``)
- ``reconnectInterval``: _Integer_ - Number of ms before attempting to reconnect (Default: ``1000``)
- ``secure``: _Boolean_ - Use secure connection (SSL / HTTPS) (_Overrides port to ``443``_)
- ``timeout``: _Integer_ - Number of ms to disconnect if no responses from server (Default: ``9999``)

``identity``: (_Optional_)

- ``username``: _String_ - Username on Twitch
- ``password``: _String_ - [OAuth password](http://twitchapps.com/tmi/) on Twitch

``channels``: _Array_ - List of channels to join when connected (Default: ``[]``)

``logger``: _Object_ - Custom logger with the methods ``info``, ``warn``, and ``error``

## Examples

### Node

~~~ javascript
var tmi = require("tmi.js");

var options = {
    options: {
        debug: true
    },
    connection: {
        reconnect: true
    },
    identity: {
        username: "Schmoopiie",
        password: "oauth:a29b68aede41e25179a66c5978b21437"
    },
    channels: ["#schmoopiie"]
};

var client = new tmi.client(options);

// Connect the client to the server..
client.connect();
~~~

### Browser
**index.html**

~~~ html
<!DOCTYPE html>
<html lang="en">
	<head></head>
	<body>
        <script src="//cdn.tmijs.org/js/1.0.0/tmi.min.js"></script>
        <script src="example.js"></script>
	</body>
</html>
~~~
**example.js**

~~~ javascript
var options = {
    options: {
        debug: true
    },
    connection: {
        reconnect: true,
    },
    identity: {
        username: "Schmoopiie",
        password: "oauth:a29b68aede41e25179a66c5978b21437"
    },
    channels: ["#schmoopiie"]
};

var client = new tmi.client(options);

// Connect the client to the server..
client.connect();
~~~
