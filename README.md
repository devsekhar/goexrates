## 💰 goexrates

A foreign exchange rates and currency conversion API. Golang implementation of [fixer.io](http://fixer.io) (Ruby). Data from European Central Bank API.

The rates are updated daily around 4PM CET.

### **Usage**

Get the latest foreign exchange reference rates in JSON format.

```http
GET /latest
Host: exr.mikolajczakluq.com
```

Get historical rates for any day since 1999-01-04.

```http
GET /2008-03-18
Host: exr.mikolajczakluq.com
```

Rates are quoted against the Euro by default. Quote against a different currency by setting the base parameter in your request.

```http
GET /latest?base=USD
Host: exr.mikolajczaluq.com
```

Request specific exchange rates by setting the symbols parameter.

```http
GET /latest?symbols=USD,GBP
Host: exr.mikolajczakluq.com
```

Response format.

```json
{
    "base": "EUR",
    "date": "2017-05-05",
    "rates": {
        "AUD": 1.4832,
        "PLN": 4.2173,
        "MYR": 4.7543,
        "USD": 1.0961,
        "...": "and so on...",
    }
}
```

### **Run**

```bash
go run goexrates.go
```

### TODO

* Requests caching

### **Important note**

Currently this API is available [here](http://goexrates.mikolajczakluq.com) but it might change at any time. I created it for **.go** learning purposes.
