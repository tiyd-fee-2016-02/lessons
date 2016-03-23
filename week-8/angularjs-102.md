# AngularJS 102

## Events

AngularJS has built-in event listeners that function much like the jQuery ones you're familiar with.

These include (but aren't limited to):

ng-click

ng-dblclick

ng-focus

ng-keydown

ng-keypress

ng-keyup

ng-mouseover

## Filters

Filters are simple functions that you can call from Angular views to modify the way that data is displayed.

Here's an example of a built-in filter called currency:

    {{price | currency}}

It modifies the way that price is displayed, adding $, and
other fancy things.

You can write your own filters as well by using `.filter` and writing a function in your `.js` file.

## Very useful!

* [Giant documented list of ng directives](https://docs.angularjs.org/api/ng#directive)
* [Built-in filters](https://docs.angularjs.org/api/ng#filter)
* [Top 10 Mistakes AngularJS Devs Make](https://www.airpair.com/angularjs/posts/top-10-mistakes-angularjs-developers-make)
* [Learn-Angular.org](http://www.learn-angular.org/)
