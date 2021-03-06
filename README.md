Integrating the "rightsservice" with Splash
===========================================

This package is part of the Mouf PHP framework and contains the @RequiresRight annotation that integrates Splash with the RightsService.

If you are using the Splash MVC framework, there is a special package to help you
integrate the "rightsservice" with Splash or Druplash. The package name is "security/rightsservice_splash".

This package provides a number of useful filters:

The <b>@RequiresRight</b> annotation
------------------------------------

This filter can be used in any action. If you put this annotation, the user will be denied access
if he does not possess the specified right.

```php
/**
 * A sample default action that requires to have the "ACCESS_ADMIN_RIGHT" right.
 *
 * @URL /admin
 * @RequiresRight(name="ACCESS_ADMIN_RIGHT")
 */
public function defaultAction() { ... }
```

The <b>@RequiresRight</b> annotation requires an instance of <a href="rightsservice_package.html">RightsService</a> to exist. The
name of the instance must be "rightsService".
If your RightsService instance is not named "rightsService" (or if you want to use several RightsService instances,
you can specify the instance of UserService to use in parameter of the annotation:

```php
/**
 * A sample default action that requires to have the "ACCESS_ADMIN_RIGHT" right.
 *
 * @URL /admin
 * @RequiresRight(name="ACCESS_ADMIN_RIGHT",instance="myRightService")
 */
public function defaultAction() { ... }
```
