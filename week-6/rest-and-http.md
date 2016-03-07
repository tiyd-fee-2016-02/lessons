# HTTP Protocol and RESTful Architecture

## HTTP protocol

HTTP (HyperText Transfer Protocol) is used to make a lot of things happen on the web.

Ever wondered why a webpage loads when you type a URL in your browser? It's because it's sending an HTTP command that says, hey! Fetch and transmit that page!

You've been using HTTP protocol already -- every AJAX request is an HTTP request. Yep, that means GET, POST, PUT, DELETE.

## HTTP Status Codes

We're all used to 404 error messages. But what exactly does it mean? What do all the *other* status codes mean?

Thank goodness we have [HTTP Status Cats](https://http.cat/)!

HTTP Status Codes help you debug your program and trace errors easier.

## RESTful Applications

REST stands for *Representational State Transfer*. It's an architecture style specifically used for designing networked applications. It uses the HTTP protocol to do this. REST really matters on the back end, but as more web applications are built with front-end frameworks, it's becoming more and more important to become familiar with it.

With REST, every resource has its own URL and you use different HTTP methods to interact with those resources.

*With thanks to [REST API Tutorial](http://www.restapitutorial.com/lessons/restfulresourcenaming.html)*

`http://www.example.com/customers/33245/orders`

What do you think the above site leads to? What if we take everything after `customers` off? What would you expect to get in return?

What about `https://github.com/kellymurray/simple-vue-js-demo`?

Or:

`http://example.com/script.php?method=get_post&blogid=842`

Is that an example of a RESTful URL structure? Why or why not?

## Resources

[Beginner's Guide to HTTP and REST](http://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340)

[JSON Placeholder](http://jsonplaceholder.typicode.com/)
