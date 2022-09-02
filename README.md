# Cheat Sheet for all basic commands of Redis


# Get all data from a list in Node : 

```
value = client.lRange("name", 0,10);
    value2 = Promise.resolve(value);
    value2.then(function (value) {
        res.send(value);
    });
    
/* 
return : 
[
    "Antoine",
    "Anthony",
    "Baptiste",
    "Maxim"
]
*/
```
