# API stub server

This code has the purpose to be an example project to setup a stub server for any API.

## Pre requisites

You should have node, npm & git installed. You can check this in cli:

```
node -v && npm -v && git --version
```

## Running the stub server

1. Clone the project
2. Run `npm install`
3. Run the server: `npm run api`
4. Open up the graphical interface: [http://localhost:1880](http://localhost:1880)

**Username**: nodered  
**Password**: password

## Documentation

This project uses the great NodeRED. So special thanks to the IBM guys working on it. You can find some more info
about the tool using the following

- NodeRED website: http://nodered.org/
- Documentation: http://nodered.org/docs/
- Github: https://github.com/node-red/node-red

## Accessing endpoints

To quickly setup this project and checkout the examples I suggest you to install Postman.

You can use the examples provided as a Postman export. Just import the `api-stub-server.postman_collection.json` file
in your postman setup. It is defined as a collection with the same name as this project. 

## Examples

You can always run the API stub server by doing this commands:

```
npm run api
```

### Creating different endpoints

This example shows how to create several endpoints. Load it by going to tab "endpoints" in the canvas. It might be 
useful to check the impact of a slow API on your application. In the canvas you can see the function `Random delay 1-3s` 
that slows down the request.

You can implement the various HTTP methods POST, GET, PUT & DELETE The examples provided won't do actual writing in 
any DB. It just shows the possibilities. Check it out by using the `News overview`, `News detail GET`, 
`News detail PUT` & `News overview POST` examples in the Postman export.

### Enable debug logging (1)

This example shows how to have a in NodeRED to disable or enable debug loggin on runtime. Load it by going to tab 
"debug logging" in the canvas. In the canvas you will have an injector to enable or disable. Try playing around with 
the toggle. You can do this by starting the `FAQ overview` request in the postman example.

This is just an example on how to enable debugging based on the request. You can basically output anything that is 
related to the request or response in your debug function.

### Enable debug logging (2)

This example is quite similar to the previous one. Instead of using a switch in NodeRed to enable or disable the logging
of debug information, we set in via an argument. 

Stop your server and run the api by setting the --debug option.

```
npm run api --debug
```

Now you don't need the toggle to enable or disable the debugging. Debugging is set by default.


### Differentiating the responses from an endpoint (1)

It's possible to differentiate between the responses coming back from the same API. This might be usefull when you want 
to test an endpoint that might have different structure based on some environment setting. For example a logged in user
versus a guest user.

Enable the guest user by clicking in front of the inject node with the name "Guest User". Try the same for the 
authenticated user by injecting it. When you do a call the `search/result` endpoint you will see that it differs.

### Differentiating the responses from an endpoint (2)

This example is quite similar to the previous one. Instead of using a switch in NodeRed we control it via the Headers in
the request. Agian, you can use the /search/result endpoint for this example.

Try now to disable or enable the X-Application-Token header in the `search/result` endpoint and issue the request.

## Contributors

Sam Vloeberghs - [@samvloeberghs](https://twitter.com/samvloeberghs) - [sam.vloeberghs@gmail.com](mailto:sam.vloeberghs@gmail.com)

## Courtesy & acknowledgment