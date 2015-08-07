This is a Matrix Application Service framework written in Node.js.

This can be used to quickly setup performant application services for almost 
anything you can think of in a web framework agnostic way.

``` javascript
var AppService = require("matrix-appservice").AppService;
var AppServiceRegistration = require("matrix-appservice").AppServiceRegistration;

// creating registration files
var reg = new AppServiceRegistration();
reg.addRegexPattern("users", "@.*", true);
reg.outputAsYaml("registration.yaml");

// listening
var as = new AppService({
  homeserverToken: "abcd653bac492087d3c87"
});
as.on("type:m.room.message", function(event) {
  // handle the incoming message
});
as.on("query:user", function(userId) {
  // handle the incoming user query
});
as.listen(8010);
```

API Reference
=============

A hosted API reference can be found on GitHub Pages.

