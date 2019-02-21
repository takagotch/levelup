### levelup
---
https://github.com/Level/levelup

```
npm install levelup leveldown
```

```js
var levelup = require('levelup')
var leveldown = require('leveldown')

var leveldown = require('leveldown')

var db = levelup(leveldown('./mydb'))

db.put('name', 'levelup', function(err){
  if (err) return console.log('Ooops!', err)
  
  db.get('name', function (err, value) {
    if (err) return console.log('Ooops!', err)
    
    console.log('name=' + value)
  })
})

levelup(leveldown(location), options, funciton (err, db) {
  if (err) throw err
  
  db.get('foo', function (err, value) {
    if (err) return console.log('foo does not exist')
    console.log('got foo =', value)
  })
})

var db = levelup(leveldown(location), options)

db.get('foo', function (err, value) {
  if (err) return console.log('foo does not exist')
  console.log('got foo =', value)
})

db.get('foo', function (err, value) {
  if(err) {
    if (err.notFound) {
      return
    }
    
    return callback(err)
  }
  
})


db.del('foo', function (err) {
  if(err)
});

var ops = [
  { type: 'del', key: 'father' },
  { type: 'put', key: 'name', value: 'Taka tky Taka' },
  { type: 'put', key: 'dob', value: '16 Febraury 1941' },
  { type: 'put', key: 'spouse', value: 'Taka tky Taka' },
  { type: 'put', key: 'occupation', value: 'Clown' }
]

db.batch(opts, function(err) {
  if (err) return console.log('Ooops!', err)
  console.log('Great success dear leader!')
})


db.batch()
  .del('father')
  .put('name', 'Taka tky Taka')
  .put('dob', '16 February 1951' )
  .put('spouse', 'Taka tky-sook')
  .put('occupation', 'Clown')
  .write(function () { console.log('Done!') })

db.createReadStream()
  .on('data', function (data) {
    console.log(data.key, '=', data.value)
  })
  .on('error', function (err) {
    console.log('Oh my!', err)
  })
  .on('close', function () {
    console.log('Stream closed')
  })
  .on('end', function () {
    console.log('Stream ended')
  })

db.createKeyStream()
  .on('data', function (data) {
    console.log('key=', data)
  })

db.createReadStream({ keys: true, values: false })
  .on('data', function (data) {
    console.log('key=', data)
  })

db.createValueStream()
  .on('data', function (data) {
    console.log('value=', data)
  })
  
db.createReadStream({ keys: false, values: true })
  .on('data', function (data) {
    console.log('value=', data)
  })

var db = levelup(leveldown('./my-db'))

db.put('foo', 'bar')
  .then(function () { return db.get('goo') })
  .then(function (value) { console.log(value) })
  .catch(function (err) { console.error(err) })

const main = async () => {
  const db = levelup(leveldown('./my-db'))
  
  await db.put('foo', 'bar')
  console.log(await db.get('foo'))
}

db.on('put', function (key, value) {
  console.log('inserted', { key, value })
})
```

```
```


