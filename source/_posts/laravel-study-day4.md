title: "laravel study day4"
date: 2015-04-27 09:43:34
tags:
- web
- laravel
- php
---

## Validation

#### way to use validator:
- Facade: Validator::make($data, $rule), data and rule should be an array.
- Controller use a trait, inside Controller, we can directly call $this->validate($request, $rule)
- Create a NewRequest, and use type-hint in the controller method.

If fail validator, will go back and store error messages in session. or send back 422 code for Ajax request.

## Eloquent ORM

Inside Model class, $table use to indicate table, $primaryKey indicated key($increment should also be setup false), $connection to switch mutilple tables. $timestamp to create create_at, update_at two columns.

scopeGaga(), magic method, we can use ->gaga() in Model to limit search

### table relations
1. hasOne() & belongsTo
2. hasMany() & belongsTo
3. belongsToMany() and belongsToMany()
