# hook.js - alpha

the easiest way to build real-time web applications

# Usage

Just include this on any page:

     <script type="text/javascript" src="hook.js"></script>

Now you have access to the "hook" object. The hook object is special object which
gives you the ability to seamlessly call server events from the browser and browser events from the server.

## NOTE

The latest stable version of hook.js is 0.8.0 and can run by executing the following commands:

Grab the latest stable branch

``` git clone https://github.com/hookio/hook.js.git ```

Navigate into the hook.js directory

``` cd hook.js ```

Check out the latest branch

``` git checkout 0.8.0 ```

Start the hook.js server

``` ./bin/server ```

Visit the secret dashboard

``` http://localhost:9003/dashboard.html ```

<h3>Emitter API</h3>

``` js
// Browser
hook.emit('hello', 'dog');

// Server
hook.on('browser::hello', function(data){
  // outputs 'dog'
  console.log(data);
});
```

<h3>Emitter Callback API</h3>
``` js
// Browser
hook.emit('hello', function(err, result){
  // outputs 'sup'
  console.log(result);
});

// Server
hook.on('browser::hello', function(callback){
  callback(null, 'sup');
});
```