# Cheat Sheet for all basic commands of Redis


# Get all data from a list in Node : 

```
value = client.lRange("name", 0,10);
    value2 = Promise.resolve(value);
    value2.then(function (value) {
        res.send(value);
    });
    
//
// return : 
// [
//    "Antoine",
//    "Anthony",
//    "Baptiste",
//    "Maxim"
// ]

```


# Connexion au serveur distant depuis le terminal
```
redis-cli -u redis://password@host:port

```

# Connexion au serveur distant depuis nodejs
```
const client = redis.createClient({
    url : 'redis://username:password@host:port'
});

(async () => {
    try {
      await client.connect();
      console.log('Connected to redis');
    } catch (err) {
      console.error(err)
    }
  })()

client.on('connect', () => {
    console.log('Redis client connected');
});

client.on('error', (err) => {
    console.log('Something went wrong ' + err);
});
```
