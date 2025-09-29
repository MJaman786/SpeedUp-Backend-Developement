## install the libraries and packages

### 1. Configuring npm 
``` bash
npm init -y
```

### 2. Installing Libraries
``` bash
npm i express nodemon ejs
```

### 3. Code for Creating a Server in Nodejs
``` javascript
// built in module
const http = require('http')

//import user defined module 
const result = require('./calculator')

const app = http.createServer((req, res) => {

    // header set for html content
    res.writeHead(200, { 'content-type': 'text/html' })

    res.write("<h1>Welcome To Node JS Server !!</h1>")
    res.write("<h1>Welcome To Node JS Server !!</h1>")
    res.write("<h1>Welcome To Node JS Server !!</h1>")

    console.log(result.sum(10, 30, 40))
    res.write(`
        
        <h2>Your Name is ${result.obj.name}</h2>        

    `)

    res.end("response end")

})

const PORT = 3000;
const HOST = '127.0.0.1';

// must port 
app.listen(PORT, HOST, () => {
    console.log(`server is running http://${HOST}:${PORT}`)
})

```

### 4. Code for Creating a Server in Expressjs

``` javascript
// Import express
const express = require('express');

// Create an app object
const app = express();

// Define a port
const PORT = 3000;

// Middleware (optional) – to serve static files
app.use(express.static('public'));

// Define routes
app.get('/', (req, res) => {
  res.send('Hello, Express Server is running 🚀');
});

app.get('/about', (req, res) => {
  res.send('This is the about page');
});

// Start the server
app.listen(PORT, () => {
  console.log(`✅ Server is running at http://localhost:${PORT}`);
});

```