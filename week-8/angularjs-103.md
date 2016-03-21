### AJAX with Angular

Angular provides an $http object which is used to make AJAX calls.

    https://docs.angularjs.org/api/ng/service/$http

It works like this:

    $http.get('http://the.url/you/want/to/get')
      .then(function (result) {
        // This is called if the AJAX promise succeeded. It is similar to
        // jQuery's success method.
        //
        // result is the result of the get operation. It has lots of info
        // associated with it. But its data property is what gives you
        // the data that was returned from the server.
        return result.data;
      })
      .catch(function (error) {
        // The catch function is called if the AJAX promise failed.
        // It is similar (but not exactly) like jQuery's .fail method.
      });

If you wanted to post data to a server:

    $http.post('http://the.url/etc/etc', { foo: 'bar' })
      .then(function (result) { })
      .catch(function (error) { });

If you wanted to put, call `$http.put`

    $http.put('http://the.url/etc/etc', { foo: 'bar' })
      .then(function (result) { })
      .catch(function (error) { });

If you wanted to delete, call: `$http.delete`

    $http.delete('http://foo.bar/baz/bleh')
      .then(function (result) { })
      .catch(function (error) { });

AJAX should be done in a service/factory object, not directly in controllers.

You can see an example of a AJAX service here:

    https://github.com/tiy-durham-fe-2015/gulp-angular/blob/master/src/components/services/users/users-service.js

And you can see how to consume such an object here:

    https://github.com/tiy-durham-fe-2015/gulp-angular/blob/master/src/users/users-controller.js

Let's break that last bit down:

    // Here, we are defining the '#/users' page...
    app.config(['$routeProvider', function($routeProvider) {
      // Route definition looks pretty similar to what we've already seen...
      var routeDefinition = {
        templateUrl: 'users/users.html',
        controller: 'UsersCtrl',
        controllerAs: 'vm',

        // Except this! Here, we are saying, when this route runs, first
        // resolve these dependencies:
        resolve: {
          // The users dependency users our usersService AJAX object to
          // fetch a list of users from GitHub. The controller will not be
          // called until the users list has been successfully loaded...
          // Angular will wait for the AJAX promise to succeed, then it will
          // take the result of that promise and stick it in a dependency called
          // 'users'.
          users: ['usersService', function (usersService) {
            return usersService.list();
          }]
        }
      };

      $routeProvider.when('/', routeDefinition);
      $routeProvider.when('/users', routeDefinition);
    }])
    .controller('UsersCtrl', ['users', function (users) {
      // In our controller definition, we are injecting the 'users' dependency
      // which is the value returned from our AJAX call.
      this.users = users;
    }]);
