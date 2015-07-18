title: "laravel study day2"
date: 2015-04-25 12:29:52
tags:
- web
- laravel
- php

---

## Controller

Route::get('foo', ['uses' => 'FooController@main', 'as' => 'fooController']);
$url = action('foo' => '\App\Http\Controller\FooControl@method')

middle can added to controller by two ways:
1. in Route, by add them to Config
2. in Controller itself, in __construct() method

`Route::controller(['url' => 'UrlController'])` register a url to a controller, inside controller, we should define some method like *requsettype+url*( like getGaga() ).

When use `php artisan make:controller` create new controller. It automatic create following restful method:
- index
- create
- store
- show
- edit
- update
- destory

we can use Route::resource($url, $controller) to register:
we in third parameter, we can use **only**, and **except** to limit the method
url1.url2 = /url/{url1}/url/{url2}
Route::resource shoule be put in the last.
