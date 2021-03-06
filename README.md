Chaos HTTP Proxy
================
Introduce failures into HTTP requests via a
[proxy server](http://en.wikipedia.org/wiki/Proxy_server).
This can uncover error handling bugs in HTTP clients.
Andrew Gaul at Bounce Storage <gaul@bouncestorage.com> originally wrote
Chaos HTTP Proxy.

Features
--------
Chaos HTTP Proxy can trigger many different failures:

* [change case of HTTP header name](http://stackoverflow.com/questions/5258977/are-http-headers-case-sensitive)
* Content-MD5 request corruption
* Content-MD5 response corruption
* client timeout, HTTP 408
* redirects (temporary and permanent)
* reorder response headers
* server errors: HTTP 500, 503, and 504
* server timeout

Installation
------------
Users can
[download releases](https://github.com/bouncestorage/chaos-http-proxy/releases)
from GitHub.
One can also build the project by running `mvn package` which produces a
binary at `target/chaos-http-proxy`.
Chaos HTTP Proxy requires Java 7 to run.

Examples
--------
Linux and Mac OS X users can run Chaos HTTP Proxy via the executable jar:

```
chmod +x chaos-http-proxy
chaos-http-proxy --properties chaos-http-proxy.conf
```

Windows users must explicitly invoke java:

```
java -jar chaos-http-proxy --properties chaos-http-proxy.conf
```

[Sample configuration](https://github.com/bouncestorage/chaos-http-proxy/blob/master/src/main/resources/chaos-http-proxy.conf)

Limitations
-----------
* lacks HTTP authentication
* lacks HTTPS support

References
----------
* [Charles Web Debugging Proxy](http://www.charlesproxy.com/) - allows interactive modification of HTTP requests and responses
* [Chaos Monkey](https://github.com/Netflix/SimianArmy) - inspiration for Chaos HTTP Proxy
* [Hamms](https://github.com/kevinburke/hamms) - designed to elicit failures in your HTTP Client, similar to httpbin
* [httpbin](http://httpbin.org/) - HTTP Request & Response Service which can deterministically exercise HTTP functionality
* [pathod](http://pathod.net/docs/pathod) - programmable HTTP server
* [Vaurien](https://github.com/mozilla-services/vaurien) - Chaos TCP Proxy

License
-------
Copyright (C) 2015 Bounce Storage

Licensed under the Apache License, Version 2.0
