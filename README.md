# Vault of Satoshi API
[![NPM](https://nodei.co/npm/vos-api.png)](https://nodei.co/npm/vos-api/)


# Install
`npm install vos-api`

# No Affiliation with VOS
`This is an UNOFFICIAL Vault of Satoshi client library!`

# Endpoint Support
```
/public/ticker          Get trading statistics
/public/orderbook       Get the list of open orders/price levels
/info/currency          Get information about supported currencies
/info/account           Get information about an Api-Key and account
/info/balance           Get wallet balances
/info/wallet_address    Get addresses of wallets
/info/wallet_history    Get list of transfer into/out of wallet
/info/ticker            Get trading statistics
/info/quote             Get quote for a trade
/info/orderbook         Get the list of open orders/price levels
/info/orders            Get information about your orders
/info/order_detail      Get list of transactions resulting from an order
/trade/place            Place an order
/trade/cancel          Cancel an order
```

# API Keys/Documentation
You need to generate your own API key/secret combination on the Vault of Satoshi 
site. 

[https://www.vaultofsatoshi.com/api](Vault of Satoshi)

# How it works
```javascript
var vos = require('vos-api')('key','secret');

var currency_pair = {
    order_currency: 'btc',
    payment_currency: 'usd'
};

function callback(ticker_data) {

}
vos.Public.ticker(currency_pair, callback);
```


## Accessing Endpoints via Code
All endpoints are in the format `vos[Public|Info|Trade].endpoint`. 

```javascript
vos.Public = {
    ticker: function(options, callback),
    orderbook: function(options, callback)
};

vos.Info = {
   currency: function(options, callback),
   account: function(options, callback),
   balance: function(options, callback),
   quote: function(options, callback),
   orderbook: function(options, callback),
   orders: function(options, callback),
   order_detail: function(options, callback),
   wallet: {
        address: function(options, callback),
        history: function(options, callback)
   }
};

vos.Trade = {
    place: function(options, callback),
    cancel: function(options, callback)
};
```
