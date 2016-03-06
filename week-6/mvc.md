# Model-View-Controller (MVC) 101

Model-View-Controller (MVC) is a software architectural pattern used to structure user interfaces. We'll specifically be talking about it in the terms of web applications.

You can break it down like so:

## Model

The **Model** represents the data. It's where the data lives.

## View

The **View** displays the model data -- it's what you see as a user. It also sends the user's actions to the Controller. The View typically has the HTML code. Example: in the case of Facebook, it's the user's wall.

## Controller

The **Controller** responds to user input and updates the Model. When you log into Facebook, a controller takes your input (name, password), finds you in the system, checks your password, and logs you in against the Model's data. It then updates the View to either show you your wall or an error message.

## MVC Helps with Separation of Concerns

I like this description from [CodeProject.com](http://www.codeproject.com/Articles/25057/Simple-Example-of-MVC-Model-View-Controller-Design):

>MVC is often seen in web applications, where the view is the actual HTML page, and the controller is the code that gathers dynamic data and generates the content within the HTML. Finally, the model is represented by the actual content, usually stored in a database or XML files, and the business rules that transform that content based on user actions.

>Though MVC comes in different flavors, control flow generally works as follows:

>The user interacts with the user interface in some way (e.g. presses a button).

>A controller handles the input event from the user interface, often via a registered handler or callback.

>The controller notifies the model of the user action, possibly resulting in a change in the model's state. (e.g. controller updates user's shopping cart).

>A view uses the model (indirectly) to generate an appropriate user interface (e.g. the view produces a screen listing the shopping cart contents). The view gets its own data from the model. The model has no direct knowledge of the view.

>The user interface waits for further user interactions, which begins the cycle anew.

>By decoupling models and views, MVC helps to reduce the complexity in architectural design, and to increase flexibility and reuse.

## What is Two-Way Data Binding?

You'll see this term around. Essentially, it means when data in the model changes, the view updates. Similarly, changes to the view should update the model.

I tried to find a good image to illustrate MVC. I gave up after ten minutes. So, your milage may vary but: [MVC Images](https://www.google.com/search?q=mvc+image&biw=1228&bih=637&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjxwbGnwqzLAhUM4iYKHYF9C8IQ_AUIBigB).
