title: "laravel study day3"
date: 2015-04-26 09:00:34
tags:
- web
- laravel
- php
---

## Auth
`Auth::attemp()` // customise auth field, first parameter is array, second option parameter could be a $remember to remember login
`Auth::check()` // check is user loged in 
`Auth::viaRemember` // to check remembered.

##### how to get a user instance:
1. use Auth::user()
2. through $request, $request->user()
3. in __construct(), through dependency injection and type int

In Route: add `'middleware' => 'auth'` to auth before process request.

***** how to process oauth back user:
```php
$user = Socialize::with('github')->user();

// OAuth Two Providers
$token = $user->token;

// OAuth One Providers
$token = $user->token;
$tokenSecret = $user->tokenSecret;

// All Providers
$user->getId();
$user->getNickname();
$user->getName();
$user->getEmail();
$user->getAvatar();
```

## Cache
cache have following methods: put, add, has, remember(get or store), pull(get then forget), `forget`

`tags()` method add tags, also group key/value pair in tags's value. tags()->flush will delete all key/value pair in that tag.
