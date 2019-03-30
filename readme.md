FUNNYMAY API v1.0 (2019-03-30)
=====================
General API Information
=====================

* The base endpoint is: https://www.funnymay.com/analytics/
* All endpoints return either a JSON object or array.
* Any endpoint can return an ERROR; the error payload is as follows:

```
{
  "status":0
}
```

LIMITS
=====================
Information of cryptocurrency data updates every 60 seconds.


Public API Endpoints
=====================

SIGNALS API
-----------------------------------

### REQUEST
```
GET http://www.funnymay.com/analytics/signal_api.php
```

### PARAMETERS
Parameter |Type     |Mandatory |Description
----------|---------|----------|--------------------
s         |STRING   |YES       |Signal type
p         |STRING   |NO        |Optional parameter

#### Signal types:
Value           |Description
----------------|----------------------
gainer          |New Gainers
loser           |New Losers
newhigh         |New Highs
newlow          |New Lows
sma20xsma50     |Crosses of SMA20 and SMA50
sma50xsma200    |Crosses of SMA50 and SMA200

### EXAMPLE
```
http://www.funnymay.com/analytics/signal_api.php?s=gainer
```

### RESPONSE
```
{
  "status":1,
  "data": [
    {
      "symbol":"RCNBTC",
      "price":0.00123456,
      "change":4.123
    },
    { ... }
  ]
}
```
