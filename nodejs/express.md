# Express

minimalist middleware based web framework for Node.js. It is a **server-side or backend** framework.

## Why use Express?

- Makes building web apps with nodejs **much easier.**
- Used for both server rendered apps as well as API/Microservices.
- Extremely light, fast and free.
- full control of request and response.
- Great to use with client side framework as it is all javascript

## Basic server syntax

```
const express = require('express'); //common-js module syntax

// Init express
const app = express();

// Create your endpoint/route handlers
app.get('/', (req, res, next) => {
    res.send('Hello World!');
})

// Listen to a port
app.listen(5000);
```

## Basic Route Handling

- Handling request/routes is simple
- app.get(), app.post(), app.put(), app.delete() etc.
- Access to params, query strings, url parts etc.
- Express has a router so we can store routes in different files and export.
- We can parse incoming data with body parser.

```
app.get('/', (req, res, next) => {
    // Fetch from DB
    // Load pages
    // Return json
    // Full Access to request and response
    next() // to Call next middleware
})

```

## Express MiddleWare

Middleware functions are functions that have access to the request and response object. Express has built in middleware but middleware also comes from 3rd party packages as well as custom middleware

- Execute any code.
- Make changes to the request/response object
- End response cycle
- Call next middleware in the stack

app.use(middlewareFunction)

Note: the order of middleware functions in the code matters. Order is Top-to-bottom.
Always call next(); in the custom middleware functions to pass the control to next middleware.

### Error Handling in Express middleware

Error handling middleware functions have four arguments - error, req, res, next
These functions can capture error in the code and respond accordingly

```
const express = require('express');
const app = express();

app.use((req, res, next) => {
    console.log('I am a middleware');
    next();
})

app.get('/',(req, res, next) => {
    const err = new Error('Something went wrong');
    next(err);
})

app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send('Internal Server Error');
})

app.listen(3000, () => {
  console.log('Server is running on port 3000');
});

```

When dealing with asynchronous code, error handling needs to be explicit. Always wrap the code in **try-catch** block.

```
app.get('/async', async(req, res, next) => {
    try{
        const response = await fetch(url);
        res.send(response);
    }catch(error){
        next(error)
    }
})
```

Logging Errors
For better debugging and monitoring, you can integrate logging mechanisms such as morgan or winston to log errors and requests.[Refer here](https://www.npmjs.com/package/morgan)

```
var express = require('express')
var morgan = require('morgan')

var app = express()

app.use(morgan('combined'))

app.get('/', function (req, res) {
  res.send('hello, world!')
})
```
