FUNNYMAY API v1.0 (2019-03-30)
=====================
General API Information
=====================

* The base endpoint is: https://www.funnymay.com/api/
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
GET http://www.funnymay.com/api/signal_api.php
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
http://www.funnymay.com/api/signal_api.php?s=gainer
```

### RESPONSE
```
{
  "status":1,
  "data": [
    {
      "signal":"Gainer",
      "symbol":"RCNBTC",
      "price":0.00123456,
      "change":4.123
    },
    { ... }
  ]
}
```


SCREENER API
-----------------------------------

### REQUEST
```
GET http://www.funnymay.com/api/screener_api.php
```
### PARAMETERS
Parameter |Type     |Mandatory |Description
----------|---------|----------|--------------------
bs        |STRING   |NO        |Base asset
qt        |STRING   |NO        |Quote asset
vr        |STRING   |NO        |Relative volume
ch        |STRING   |NO        |Change, %
qp        |STRING   |NO        |Equal in USDT
p10       |STRING   |NO        |SMA 10 settings
p20       |STRING   |NO        |SMA 20 settings
p50       |STRING   |NO        |SMA 50 settings
p100      |STRING   |NO        |SMA 100 settings
p200      |STRING   |NO        |SMA 200 settings
hl50d     |STRING   |NO        |50-day High-Low settings
hl52w     |STRING   |NO        |52-week High-Low settings
m         |STRING   |NO        |Mayer Multiple settings
d         |STRING   |NO        |Days in row settins

#### Parameters settings
All settings of screener parameters you can find in address bar after choosing nessesary settings at http://www.funnymay.com/screener.php

### EXAMPLE
```
http://www.funnymay.com/api/screener_api.php?vr=1&qp=1&d=1u
```

### RESPONSE
```
{
  "status":1,
  "data": [
    {
      "symbol":"EOSETH",
      "price":0.32914,
      "change":5.745
    },
    { ... }
  ]
}
```
