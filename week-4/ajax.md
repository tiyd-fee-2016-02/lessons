# AJAX

- Asynchronous JavaScript and XML
- Loads data quickly and asynchronously in the background without delaying the page rendering
- Allows JavaScript to ask a server for data without doing a page refresh
- Is almost never used for XML
- XML is just a bloated format (like JSON, but way more complex)

## How It Works

[jQuery AJAX docs](http://api.jquery.com/jquery.ajax/)

## What's JSON?

JavaScript Object Notation (JSON) is a way to store information in an organized, easy-to-access manner. It's very readable by human eyes.

```javascript
{
	"name": "kipling",
	"age": "5",
	"hometown": "Raleigh NC",
	"species": "cat"
}
```

This creates an object with values we can access using the variable `kipling`.

```javascript
document.write("Kipling is " kipling.age);
```

[CopterLabs](http://www.copterlabs.com/json-what-it-is-how-it-works-how-to-use-it/) has a great write-up on JSON that you should spend some time with this week.

## getJSON

- `getJSON` is a convenience function that allows you to easily get JSON from
an API endpoint that supports it

```javascript

// Get the top 100 users of github
$.getJSON('https://api.github.com/users')
   .done(function (data) {
      // The value of data depends entirely upon the API that you're calling.
      // You always have to either read the API docs carefully, or do lots of
      // testing to see what the API is returning. In this case, GitHub is
      // giving us an array of user objects each of which has lots of fields.
      console.log(data.map(function (u) {
        return u.login;
      }));
   });

```

## $.ajax

- Very flexible
- Can do anything any of the jQuery AJAX convenience methods can do

```javascript
$.ajax({
  dataType: 'json',
  url: 'https://api.github.com/users'
  method: 'GET', // This is the default, but I thought I'd show it
}).done(function (data) {
  console.log(data.map(function (u) {
    return u.login;
  }));
});
```

## Sending data to the server

```javascript
$.ajax({
  method: 'POST', // The HTTP method we are using
  url: '/api/users', // The URL we are sending data to
  contentType: 'application/json', // What we are sending as a request
  dataType: 'json' // What we are expecting as a response
  data: JSON.stringify({ name: 'Gregory', email: 'greg@example.com' })
}).done(function( msg ) {
  alert( "Data Saved: " + msg );
});

```

## HTTP Methods

- POST is usually used to create new records
- PUT is usually used to overwrite records
  - Is sometimes used for creation and/or update (also called upserting)
- DELETE is used to delete records and doesn't send data
- GET is used to get records and doesn't send data

## Handling errors

```javascript
$.getJSON('/api/users')
  .done(function( msg ) {
    alert( "Data Saved: " + msg );
  })
  .fail(function (request, status, err) {
    // If the server sent a failure body back, then err will contain that data
    // Otherwise, if there was a failure to connect or something, err will be
    // undefined.
    console.error(status, err);
  });
```

## Authenticating

Some APIs require users to be authenticated before you can call them.

There are a few ways to make this happen

- If you're calling an API in your own domain, you can just use cookies
- If you're calling an API on another domain, the API may handle auth in a few ways:
- OAuth
  - a complex handshake process
  - allows users to authorize your app with the remote domain
  - your app never actually sees the user's username and/or password
- Basic authentication
  - a simple authentication process
  - your app collects a username/password and sends it to the remote API

## Basic authentication

```javascript
$.ajax({
  dataType: 'json',
  url: 'https://yourbank.com/accountinfo'
  method: 'GET', // This is the default, but I thought I'd show it,
  beforeSend: function (xhr) {
    // Assuming username and password are defined somewhere as strings
    // btoa is a built-in function that converts a string to base64
    var base64Credentials = btoa(username + ":" + password);

    // setRequestHeader is a method of the DOM's AJAX object (XMLHttpRequest)
    // it allows us to set HTTP headers. These are key/value pairs that
    // modify the way an HTTP request is understood by the server. Here, we
    // are adding the Authorization header. For more info, see Google!
    xhr.setRequestHeader('Authorization', 'Basic ' + base64Credentials);
  }
}).done(function (data) {
  console.log(data);
});
```

## Old APIs

In the past, due to security issues, browsers didn't allow cross-origin calls.

That is, scripts running on `mydomain.com` could not make AJAX calls to
 `yourdomain.com`.

This has been fixed by CORS:

- Cross Origin Resource Sharing
- Old APIs and/or browsers still don't support this

## JSONP

Before CORS (and even now with sites like Etsy), you had to do something
called JSONP (JSON with Padding).

Essentially, this involved adding a script tag to your page:

`<script src="http://otherdomain.com/foo?callback=doSomething"></script>`

The server at otherdomain.com would send you back a script that looked like
this:

```javascript
doSomething({ name: 'Joe Shmo' });
```

So, as long as you had a `doSomething` function defined somewhere, it would
get called and passed the object `{ name: 'Joe Shmo' }`


## JSONP drawbacks

- Can't send authentication credentials
- Can't handle timeouts or networking errors gracefully (silently fails)
- Requires having global callbacks!

## JSONP with jQuery

- add the `dataType: 'jsonp'` property to the request
- end your URL with `callback=?`
- jQuery will generate a random callback under the hood so you don't have to

```javascript
$.ajax({
  url: '/oldapi?callback=?',
  type: 'GET',
  timeout: 5000, // 5 second timeout
  dataType: 'jsonp' // Tell jQuery we're doing JSONP
})
.done(function (data) {
  console.log(data);
});
```
