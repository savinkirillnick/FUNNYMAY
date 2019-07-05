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
Parameter |Type   |Mandatory |Description
----------|-------|----------|--------------------
bs        |ENUM   |NO        |Base asset
qt        |ENUM   |NO        |Quote asset
vr        |ENUM   |NO        |Relative volume
ch        |ENUM   |NO        |Change, %
qp        |ENUM   |NO        |Equal in USDT
p10       |ENUM   |NO        |SMA 10 settings
p20       |ENUM   |NO        |SMA 20 settings
p50       |ENUM   |NO        |SMA 50 settings
p100      |ENUM   |NO        |SMA 100 settings
p200      |ENUM   |NO        |SMA 200 settings
hl50d     |ENUM   |NO        |50-day High-Low settings
hl52w     |ENUM   |NO        |52-week High-Low settings
m         |ENUM   |NO        |Mayer Multiple settings
d         |ENUM   |NO        |Days in row settins

#### Parameters settings
All settings of screener parameters you can find in address bar after choosing nessesary settings at http://www.funnymay.com/screener.php

Description of the values of the parameter `bs`:

Value | Description
------|-----------------------------------------------
BTC   | Base asset of symbol (may be BTC, ETH, LTC and other kind of symbol)

Description of the values of the parameter `qt`:

Value | Description
------|-----------------------------------------------
BTC   | Quote asset of symbol (may be BTC, BNB, ETH, USDT, PAX and other kind of symbol)

Description of the values of the parameter `vr`:

Value | Description
------|-----------------------------------------------
10    | More than 10x
5     | More than 5x
2     | More than 2x
1     | More than 1x
0.5   | More than 0.5x
0.2   | More than 0.2x
-5    | Less than 5x
-2    | Less than 2x
-1    | Less than 1x
-0.5  | Less than 0.5x
-0.2  | Less than 0.2x

Description of the values of the parameter `ch`:

Value | Description
------|-----------------------------------------------
50    | More than 50%
20    | More than 20%
10    | More than 10%
5     | More than 5%
2     | More than 2%
1     | More than 1%
-50   | Less than 50%
-20   | Less than 20%
-10   | Less than 10%
-5    | Less than 5%
-2    | Less than 2%
-1    | Less than 1%

Description of the values of the parameter `qp`:

Value | Description
------|-----------------------------------------------
100   | Over 100 USDT
50    | Over 50 USDT
20    | Over 20 USDT
10    | Over 10 USDT
5     | Over 5 USDT
2     | Over 2 USDT
1     | Over 1 USDT
0.5   | Over 0.5 USDT
0.2   | Over 0.2 USDT
0.1   | Over 0.1 USDT
-50   | Under 50 USDT
-20   | Under 20 USDT
-10   | Under 10 USDT
-5    | Under 5 USDT
-2    | Under 2 USDT
-1    | Under 1 USDT
-0.5  | Under 0.5 USDT
-0.2  | Under 0.2 USDT
-0.1  | Under 0.1 USDT

Description of the values of the parameter `p10`:

Value  | Description
-------|-----------------------------------------------
b      | Price below SMA10	
b10    | Price 10% below SMA10
b20    | Price 20% below SMA10
b50    | Price 50% below SMA10
a      | Price above SMA10
a10    | Price 10% above SMA10
a20    | Price 20% above SMA10
a50    | Price 50% above SMA10
x      | Price crossed SMA10
xa     | Price crossed SMA10 above
xb     | Price crossed SMA10 below
a1020  | SMA10 above SMA20
b1020  | SMA10 below SMA20
a1050  | SMA10 above SMA50
b1050  | SMA10 below SMA50
a10100 | SMA10 above SMA100
b10100 | SMA10 below SMA100
a10200 | SMA10 above SMA200
b10200 | SMA10 below SMA200

Description of the values of the parameter `p20`:

Value  | Description
-------|-----------------------------------------------
b      |Price below SMA20
b10    |Price 10% below SMA20
b20    |Price 20% below SMA20
b50    |Price 50% below SMA20
a      |Price above SMA20
a10    |Price 10% above SMA20
a20    |Price 20% above SMA20
a50    |Price 50% above SMA20
x      |Price crossed SMA20
xa     |Price crossed SMA20 above
xb     |Price crossed SMA20 below
a2050  |SMA20 above SMA50
b2050  |SMA20 below SMA50
a20100 |SMA20 above SMA100
b20100 |SMA20 below SMA100
a20200 |SMA20 above SMA200
b20200 |SMA20 below SMA200

Description of the values of the parameter `p50`:

Value  | Description
-------|-----------------------------------------------
b      |Price below SMA50
b10    |Price 10% below SMA50
b20    |Price 20% below SMA50
b50    |Price 50% below SMA50
a      |Price above SMA50
a10    |Price 10% above SMA50
a20    |Price 20% above SMA50
a50    |Price 50% above SMA50
x      |Price crossed SMA50
xa     |Price crossed SMA50 above
xb     |Price crossed SMA50 below
a50100 |SMA50 above SMA200
b50100 |SMA50 below SMA200
a50200 |SMA50 above SMA200
b50200 |SMA50 below SMA200

Description of the values of the parameter `p100`:

Value  | Description
-------|-----------------------------------------------
b      |Price below SMA100
b10    |Price 10% below SMA100
b20    |Price 20% below SMA100
b50    |Price 50% below SMA100
a      |Price above SMA100
a10    |Price 10% above SMA100
a20    |Price 20% above SMA100
a50    |Price 50% above SMA100
x      |Price crossed SMA100
xa     |Price crossed SMA100 above
xb     |Price crossed SMA100 below
a100200 |SMA100 above SMA200
b100200 |SMA100 below SMA200

Description of the values of the parameter `p200`:

Value  | Description
-------|-----------------------------------------------
b      |Price below SMA200
b10    |Price 10% below SMA200
b20    |Price 20% below SMA200
b50    |Price 50% below SMA200
a      |Price above SMA200
a10    |Price 10% above SMA200
a20    |Price 20% above SMA200
a50    |Price 50% above SMA200
x      |Price crossed SMA200
xa     |Price crossed SMA200 above
xb     |Price crossed SMA200 below

Description of the values of the parameter `hl50d`:

Value  | Description
-------|-----------------------------------------------
nh     |New high
nl     |New low
-2h    |0-2% below high
-5h    |0-5% below high
-10h   |0-10% below high
5h     |5% and more below high
10h    |10% and more below high
20h    |20% and more below high
50h    |50% and more below high
-2l    |0-2% above low
-5l    |0-5% above low
-10l   |0-10% above low
5l     |5% and more above low
10l    |10% and more above low
20l    |20% and more above low
50l    |50% and more above low
100l   |100% and more above low

Description of the values of the parameter `hl52w`:

Value  | Description
-------|-----------------------------------------------
nh     |New high
nl     |New low
-2h    |0-2% below high
-5h    |0-5% below high
-10h   |0-10% below high
5h     |5% and more below high
10h    |10% and more below high
20h    |20% and more below high
50h    |50% and more below high
-2l    |0-2% above low
-5l    |0-5% above low
-10l   |0-10% above low
5l     |5% and more above low
10l    |10% and more above low
20l    |20% and more above low
50l    |50% and more above low
100l   |100% and more above low
200l   |200% and more above low
500l   |500% and more above low

Description of the values of the parameter `m`:

Value  | Description
-------|-----------------------------------------------
-1     |Less than 1.0
1      |More than 1.0
-2.4   |Less than 2.4
2.4    |More than 2.4

Description of the values of the parameter `d`:

Value  | Description
-------|-----------------------------------------------
1u     |Up 1 day
2u     |Up 2 days
2uu    |Up more than 2 days
5uu    |Up more than 5 days
10uu   |Up more than 10 days
-5u    |Up less than 5 days
-10u   |Up less than 10 days
2u5    |Up from 2 to 5 days
5u10   |Up from 5 to 10 days
1d     |Down 1 day
2d     |Down 2 days
2dd    |Down more than 2 days
5dd    |Down more than 5 days
10dd   |Down more than 10 days
-5d    |Down less than 5 days
-10d   |Down less than 10 days
2d5    |Down 2 to 5 days
5d10   |Down 5 to 10 days

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
