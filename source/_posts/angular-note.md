title: "angular note"
date: 2015-04-23 22:26:35
tags:
---

$dirty: data have been changed
$invaild: value enter is invalid
$error: exact error

two way to create service:
 - factory 
 - service

Dependency Injection is a software design pattern in which components are given their dependencies instead of hard coding them within the component.

injectable component in AngularJS:
- value: simpe javascript object
- factory: a functure to return value
- service: singleton js obj contain function and attributes.
- provider: internally provide factory and service
- constant: constant config value

directive: AngularJS application during bootstrap finds the matching elements and do one time activity using its compile() method of the custom directive then process the element using link() method of the custom directive based on the scope of the directive.
