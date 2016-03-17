# AngularJS 101
## The day is here...

## What is AngularJS?

* Front-End Framework
* Helps organize your JavaScript
* Faster website loading times

### Directives

A marker on an HTML tag that tells Angular to run or reference JavaScript. It's how we bind behavior. Some built-in directives include `ng-app` and `ng-model`. You can also create your own directives.

### Modules

Modules are where we write pieces of the Angular application and where we define dependencies.

To set a new module, you might write something like: `var app = angular.module('store', [])`

The `[]` is where you can put other named modules as dependencies. Otherwise, if there are no other dependencies, leave the empty array.

### Expressions

Expressions allow you to insert dynamic values into your HTML.

`{{"hello" + "world"}}`

### Scope



To quote the ng-newsletter:

>A $scope is an object that ties a view (a DOM element) to the controller. In
the Model-View-Controller structure, this $scope object becomes the model. It
provides an execution context that is bound to the DOM element (and its children).

>Although it sounds complex, the $scope is just a JavaScript object. Both the
controller and the view have access to the $scope so it can be used for
communication between the two. This $scope object will house both the data
and the functions that we’ll want to run in the view, as we’ll see.

They have a great write-up on [scope](http://www.ng-newsletter.com/posts/beginner2expert-scopes.html) that is worth the read.

## Useful Resources
* [Thinkful: AngularJS Tutorial](https://www.thinkful.com/learn/angularjs-tutorial-build-a-gmail-clone/Introduction)
* [Promises in AngularJS, Explained in a Cartoon](http://andyshora.com/promises-angularjs-explained-as-cartoon.html)
* [10 AngularJS CRUD Demos](http://angularjs4u.com/demos/10-angularjs-crud-app-demos/)
