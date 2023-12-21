# Laravel Interview Question and Answer

## What is laravel?

- Laravel is free, open-source PHP framework.
- It follows the MVC architectural pattern to develop the web applications.
- Laravel is created by Taylor Otwell in june 2011

## What is MVC?

- The Model-View-Controller (MVC) pattern is a way to organise your code that separates it into three parts: Models, Controllers and Views.

- It allows you to separate the application code from the presentation code.

## What is Composer?

- Composer is an open source package management tool that helps to install packages for PHP. For Laravel also, we require composer to install packages like intervention, Passport, JWT etc.

- We can also use composer for installing Laravel and for updating pacakges and components required for our Laravel projects.

## What is the templating engine used in Laravel?

- The template engine used in Laravel is Blade.
- The blade file has .blade.php extention.

## Which database Laravel can support?

- PostgreSQL
- MySQL
- SQLite
- SQL Server
- MongoDB(Latest Version)

## What is an artisan?

- Artisan is the command-line tool or interface for Laravel that helps the developer for building the application.

`Command artisan commands in Laravel:-`

- `php artisan serve` - For running Laravel project
- `php artisan make:controller` - For making Controller file
- `php artisan make:model` - For making Model file
- `php artisan make:migration` - For making Migration file for creating Table
- `php artisan make:seeder` - For making Sedeer file for inserting data in Table
- `php artisan down` - For enable maintenance mode
- `php artisan up` - For disable maintenance mode
- `php artisan down --retry=60` - if you want the client to refresh or page after a specified number of seconds

## What is a Service container?

A Service container is one of the most powerful tools used to manage dependencies over the class and perform dependency injections.

- A service container can be used as a registry to keep track of all the classes in use within your application.
- In addition, it also helps in binding interfaces to concrete classes.
- It is also known as IoC container.

## Describe the service provider in Laravel.

You can register services, events, etc., using a service provider before booting the application. They help inject Laravels services or your application services and dependencies.

Service providers can be defined as the central place to configure all the entire Laravel applications. Applications, as well as Laravel's core services, are bootstrapped via service providers. These are powerful tools for maintaining class dependencies and performing dependency injection. Service providers also instruct Laravel to bind various components into the Laravel's Service Container.

Most of the service providers contain below-listed functions in its file:

- Register() Function
- Boot() Function

Within the Register() method, one should only bind things into the service container. One should never attempt to register any event listeners, routes, or any other piece of functionality within the Register() method.

## What are facades?

A facade is a way to access classes available in the application's service container. The service container holds all of your application's business logic, and facades provide a "static" interface to those classes.

Laravel Facades provide static-like interface classes which are available in the application's service container. Laravel self-ships with several available facades, gives access to almost all features of Laravel. Facades also help to access a service directly from the container itself. It is described in the Illuminate\Support\Facades namespace. Hence, it is easy to use.

There are lots of Laravel facades, and they're all over the place in the framework! You can see them in any controller or view file.

You can access a facade as mentioned below

```php
use Illuminate\Support\Facades\Cache;

use Illuminate\Support\Facades\Route;

Route::get('/cache', function () {

   return Cache::get('key');

});
```

## What is Dependency injection in Laravel?

- In Laravel, dependency injection is a term used for the activity of injecting components into the user application. It’s a critical element of agile architecture. The Laravel service container is a powerful tool that manages all class dependencies and performs dependency injection.

- The Laravel service container is a tool that manages all class dependencies and performs dependency injection.

- It is a technique in which one object is dependent on another object.
- There are three types of dependency injection:

1.  Constructor injection,
2.  setter injection, and
3.  interface injection.

```php
public function __construct(UserRepository $data)

{
    $this->userdata = $data;
}
```

## What is the Repository pattern in laravel?

- The repository pattern decouples data access layers and business logic in our application. It allows objects without having to know how these objects persisted. Your business logic does not need to understand how data is retrieved. The business logic relies on the repository to get the correct data.

- This pattern makes our code cleaner and easier to maintain because we can change the implementation of our data layer without changing any related code.

## What is the Singleton design pattern in laravel?

The Singleton Design Pattern in Laravel is one where a class presents a single instance of itself. It is used to restrict the instantiation of a class to a single object. It is useful when only one example is required across the system. When used properly, the first call shall instantiate the object. After that, Laravel shall return all calls to the same instantiated object.

When working with an application that requires multiple instances of an object, it can be hard to manage them all and ensure another part of your codebase is not changing them.

There are many ways you could handle this issue:

- Use a static variable inside your class and update it manually each time you want to use it
- Use a global variable and check if it's set before using it
- Use dependency injection (you'll need this if you want to inject services into your classes)

## What are the advantages of Queue?

Laravel queues are a great way to handle time-consuming tasks. They allow you to offload work from your web server, so your users don't have to wait for a response from your API before getting the next page.

Queues are also helpful if your application has multiple servers and you want to use them all without having jobs interfere with each other. For example, if one server is running PHP code while another is running Python code, they shouldn't be able to interfere with each other's processes.

Time-consuming tasks can make an interface unresponsive. You must run such tasks in the background. In Laravel, queues are a way to run these tasks in the background so that your main threads will remain responsive.

## What are Events in Laravel?

Events are great for decoupling different parts of your application. For example, suppose you want to send a Slack notification each time an order has been shipped instead of coupling your order processing code to your Slack notification code. In that case, you can raise an App\Events\OrderShipped event that the listener can receive and use to dispatch a Slack notification.

Each time you generate an event or listener, the event will store it in its directory.

Events are typically stored in the app/Events directory, while their listeners are stored in app/Listeners. You can see these directories by running `PHP artisan make: event OrderShipped.`

You don't have to worry about these directories if you don't see them in your application. They'll be created for you as you generate events and listeners using Artisan console commands.

## What is tinker in Laravel?

Laravel Tinker is a powerful REPL tool used to interact with the Laravel application with the command line in an interactive shell. Tinker came with the release of version 5.4 and is extracted into a separate package.

Tinker is an excellent tool for debugging and exploring your code. You can use it to inspect variables, models, classes, and methods at runtime. You can change anything in the console, and it will instantly update the page you are working on.

For Installing tinker, you can use composer require laravel/tinker.To execute tinker, we can use the php artisan tinker command.

## What is a REPL?

REPL stands for Read—Eval—Print—Loop. It's a type of interactive shell that takes in single user inputs, processes them, and returns the result to the client.

If you've ever used a programming language like Ruby or Python, you've probably used a REPL. They're extremely useful for testing snippets of code and running little experiments on your computer.

## What is the difference between the Get and Post method?

Both Get and Post are used to retrieve input values in Laravel. A limited amount of data in the header is allowed in the Get method, whereas the Post method allows sending large amounts of data in the body.

## Define accessors and mutators.

Accessors allow you to change the data after acquiring it from the database. And mutators enable you to modify data before saving it to a database.

## What are relationships in Laravel?

relationships also serve as influential query builders, defining relationships as methods provides powerful method chaining and querying capabilities.

Following are the types of relationships in Laravel

- One To One relationship.
- One To Many relationships.
- Many To Many relationships.
- Has Many Through relationships.
- Polymorphic relationships.
- Many To Many Polymorphic relationships.

## What is throttling and how to implement it in Laravel?

Throttling is a great way to rate-limit requests from a particular IP. This can be used to prevent DDOS attacks as well. Laravel provides a middleware that can be applied to routes, which can be added to the global middleware list as well.

You can implement throttling as below:

```php
Route::middleware('auth:api', 'throttle:60,1')->group(function () {
    Route::get('/user', function () {
        //
    });
});
```

## Name some common tools used to send emails in Laravel.

- SwiftMailer
- SMTP
- Mailgun
- Mailtrap
- Mandrill
- Postmark
- Amazon SES (Simple Email Service)
- Sendmail

## What is Forge?

Serve Management & Application Deployment Service.

## Explain traits in Laravel.

Laravel traits are a group of functions that you include within another class. A trait is like an abstract class. You cannot instantiate directly, but its methods can be used in concreate class.

PHP Traits is a group of methods which can be included within another class. A Trait cannot be instantiated by itself like an abstract class. Traits are generated to reduce the limitations of single inheritance in PHP. It allows a developer to reuse sets of methods freely in various independent classes living in different class hierarchies.

```php
trait Sharable {
public function share($item)
  {
return 'share this item';
  }
}
```

We can then include this Trait within other classes like:

```php
class Post {
use Sharable;
}
class Comment {
use Sharable;
}
```

Now, if we want to create new objects out of these classes, we would find that they both have the share() method available:

```php
$post = new Post;
echo $post->share(''); // 'share this item'
$comment = new Comment;
echo $comment->share(''); // 'share this item'
```

## Explain the concept of cookies.

Cookies are small file sent from a particular website and stored on PC by user’s browser while the user is browsing.

## What is a session in Laravel?

Session is used to pass user information from one web page to another. Laravel provides various drivers like a cookie, array, file, Memcached, and Redis to handle session data.

## What is Ajax in Laravel?

Ajax stands for Asynchronous JavaScript and XML is a web development technique that is used to create asynchronous Web applications. In Laravel, response() and json() functions are used to create asynchronous web applications.

## State the difference between authentication and authorization.

Authentication means confirming user identities through credentials, while authorization refers to gathering access to the system.

## What are policies classes?

Policies classes include authorization logic of Laravel application. These classes are used for a particular model or resource.

## What do you mean by Laravel Dusk?

Laravel Dusk is a tool which is used for testing JavaScript enabled applications. It provides powerful, browser automation, and testing API.

## Explain Laravel echo.

It is a JavaScript library that makes possible to subscribe and listen to channels Laravel events. You can use NPM package manager to install echo.

## What is query scope?

It is a feature of Laravel where we can reuse similar queries. We do not require to write the same types of queries again in the Laravel project. Once the scope is defined, just call the scope method when querying the model.

## What is an Observer?

Model Observers is a feature of Laravel. It is used to make clusters of event listeners for a model. Method names of these classes depict the Eloquent event. Observers classes methods receive the model as an argument.

## What do you know about CSRF token in Laravel? How can someone turn off CSRF protection for a specific route?

CSRF protection stands for Cross-Site Request Forgery protection. CSRF detects unauthorized attacks on web applications by the unauthorized users of a system. The built-in CSRF plug-in is used to create CSRF tokens so that it can verify all the operations and requests sent by an active authenticated user.

To turn off CSRF protection for a specific route, we can add that specific URL or Route in $except variable which is present in the app\Http\Middleware\VerifyCsrfToken.phpfile.

```php
classVerifyCsrfToken extends BaseVerifier{
protected $except = [
          'Pass here your URL',
      ];
}
```

## What do you know about Closures in Laravel?

In Laravel, a Closure is an anonymous method which can be used as a callback function. It can also be used as a parameter in a function. It is possible to pass parameters into a Closure. It can be done by changing the Closure function call in the handle() method to provide parameters to it. A Closure can access the variables outside the scope of the variable.

```php
function handle(Closure $closure) {
    $closure();
}
handle(function(){
echo 'Interview Question';
});

```
