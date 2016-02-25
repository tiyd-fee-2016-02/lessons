# Local Storage

Local Storage saves persistent data without the use of server-side technology. This is great for building prototypes and testing. It's also useful if the user is offline and needs to access their information. And great news! It's already part of the HTML5 API.

To use it, you just need to modify the `localStorage()` object in the JavaScript. The cleanest way to do this is to use the `setItem()` and `getItem()` methods.

```JavaScript
localStorage.setItem('pokemon','Luxray');
```

Need to access the info?

```JavaScript
var pokemon = localStorage.getItem('pokemon');
```

Need to remove it?

```JavaScript
localStorage.removeItem('pokemon');
var pokemon = localStorage.getItem('pokemon');
```

You can use the localStorage object with the DOM just as you would any object.

With credit to [HTMLDog](http://htmldog.com/guides/javascript/advanced/localstorage/):

Local storage can only save strings, so storing objects requires that they be turned into strings using `JSON.stringify` - you can’t ask local storage to store an object directly because it’ll store “[object Object]”, which isn’t right at all!

That also means the object must be run through `JSON.parse` on the way out of local storage. You can see this in the example below.


```javascript
localStorage.setItem('user', JSON.stringify({
    username: 'htmldog',
    api_key: 'abc123xyz789'
}));

var user = JSON.parse(localStorage.getItem('user'));
```

## Resources

Spend some time with the following resources to fully understand the power of `localStorage()`.

* [Local Storage and How to Use It On Websites](https://www.smashingmagazine.com/2010/10/local-storage-and-how-to-use-it/)
* [HTML5 Features: Storage](http://www.html5rocks.com/en/features/storage)
* [Building HTML5 Mobile Apps with Local Storage and Topcoat](https://www.binpress.com/tutorial/local-storage/106)
* [Using Local Storage](http://learn.ionicframework.com/formulas/localstorage/)
* [MDN: Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
* [How to Use Local Storage for JavaScript](http://www.webdesignerdepot.com/2013/04/how-to-use-local-storage-for-javascript/)
