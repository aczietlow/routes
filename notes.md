# Routes

## Outline

* Routes 101
* Drupal 7 -> Drupal 8
* Request pipeline
* cool things we can do wtih routes

## Drupal 8 routes

* Creating pages
  * First, define the URL for the page via a route
  * Second, create a controller for that page
    * Think of controllers as a magically thing that builds the page

Creating a simple route

```
sample_recipes:
  path: /muffin
  defaults:
    _controller: Drupal\sample_recipes\Controller\RecipeController::muffin
  requirements:
    _permission: 'access content'
```

Creating a simple controller

```
<?php

namespace Drupal\sample_recipes\Controller;

use Symfony\Component\HttpFoundation\Response;

class RecipeController {
  public function muffin() {
    return new Response('Muffins!');
  }
}
```

Clear the cache

* This is Drupal 8, we don't clear the cache anymore!
* Rebuild the cache
* `drush cr` or `drupal route:rebuild`


Ref:
https://github.com/palantirnet/slides-d8-mod-dev.git
https://www.drupal.org/docs/8/converting-drupal-7-modules-to-drupal-8/d7-to-d8-upgrade-tutorial-convert-hook_menu-and-hook
http://knpuniversity.com/screencast/drupal8-under-the-hood/debugging#play
https://slides.com/techsoldaten