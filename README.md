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

# Get hash data depuis le terminal

```
hget <key> <field>
```

# Set hash depuis nodejs

```
    client.hSet('62f976d26779729214078b2e', {
        'username': 'username',
        'email': 'email@gmail.com',
        'password': 'password',
        'avatar': 'assets/girl.png',
        'premium' : 2,
        'datecreation' : "2022-08-15T22:44:47.581Z",
        'statut' : 1,
        'admin' : 1,
        'notifications' : 0,
        'online' : 0,
        'last_connection' : "2022-08-30T16:55:22.610+00:00"
      }, // add time limit to the key
      redis.print);


```
# Set expiration date to a key in nodejs
```
client.set('my test key', 'my test value', redis.print);
client.expire('my test key', 120);

OR
client.setEx('my test key', 30, 'my test value', redis.print);

```    

# res.send(key) in nodejs
```
    value = client.get('my test key');
    value2 = Promise.resolve(value);
    value2.then(function (value) {
    res.send(" Le nom assigné est " + value);
```
