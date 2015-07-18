title: "laravel study day1"
date: 2015-04-24 20:02:19
tags:
- web
- php
- laravel
---

### Route:

> Route:get($url, $callback)
> Route:post($url, $callback)
> Route:match(['get', 'post'], $url, $callback)
> Route:any('url', $callback)

**Second parameter in method could be an array**; like ['as' = 'profile', $callback]$callback can also replace by `'use' => 'controller'`
Now we can get the url of Route:
$url = $route('profile');
$redirect()->route('profile');

$url = user/{id}  // $route->input('id') to get para.
->where('id', '[0-9]+') // append where method to limit.

by using Route::group() give all url in group following attribute: 
- middleware add middleware to all url.
- namespace give all url group a fixed namespace
- domain give subdoain
- prefix add prefix

##### to proof csrf: in input
``` html
<input type="hidden" name="_token" value="<?php echo csrf_token(); ?>">
```


- - -
