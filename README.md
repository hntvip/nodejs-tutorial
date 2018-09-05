# nodejs-tutorial

* Description: Add example and tutorial of nodejs server side

# 1. Using Express generator installs structure of a new project
  <code>npm install express-generator --save</code> 
  <br/> 
  Generator : <code> express --view=pug myapp </code> 
    <br/>
    <br/> Install depenacy:
    <br/> 
    <br/>     <code>  cd myapp  </code> 
    <br/>     <code>npm install </code> 
    <br/> 
  <br/> More information at: <a link="https://expressjs.com/en/starter/generator.html"> https://expressjs.com/en/starter/generator.html </a> 
# 2. Import some plugins to this project
adadasd
# 3. Routing
  *3 ways to define a route on project
  1. Use Route methods: <br/>
    <code>
      // GET method route <br/>
      app.get('/', function (req, res) {
        res.send('GET request to the homepage')
      })
      // POST method route <br/>
      app.post('/', function (req, res) {
        res.send('POST request to the homepage')
      })
      // DELETE method route <br/>
      app.delete('/', function (req, res) {
        res.send('DELETE request to homepage');
      });
      // PUT method route <br/>
      app.put('/', function (req, res) {
        res.send('PUT request to homepage');
      });
    </code>
    
   2. Use Route app.METHOD: <br/> 
    <code> app.METHOD(path, callback [, callback ...]) </code>
    <br/> Can use next('route') on middleware function 
    
   3. Use app.all <br/> same as METHO but can not use next('route')
    <code> 
      <br/>  app.all('/secret', function (req, res, next) {
      <br/>  console.log('Accessing the secret section ...')
      <br/>  next() // pass control to the next handler
      <br/>  });
    </code>
    </br> *<u>More informations at</u> : <a link="https://expressjs.com/en/4x/api.html#app.METHOD"> https://expressjs.com/en/4x/api.html#app.METHOD </a> <br/>
    
*Path Pattern:
    
- This will match paths starting with `/abcd` and `/abd`:<br/>
  
<pre>
  app.use('/abc?d', function (req, res, next) {
    next();
  });
</pre>

- This will match paths starting with `/abcd`, `/abbcd`, `/abbbbbcd`, and so on: <br/>

<pre> 
  app.use('/ab+cd', function (req, res, next) {
    next();
  });
</pre>

- This will match paths starting with `/abcd`, `/abxcd`, `/abFOOcd`, `/abbArcd`, and so on: <br/>

<pre> 
    app.use('/ab\*cd', function (req, res, next) {
       next();
    });
</pre> 

- This will match paths starting with `/ad` and `/abcd`: <br/>
<pre>
  app.use('/a(bc)?d', function (req, res, next) {
    next();
  });
</pre>
    
