# placeload.js

[![NPM version][npm-image]][npm-url]

The best way to create a placeholder layout effect.

What is it?
-------------

Placeload.js is a library to customize your interface previews/skeleton screen that yield a fantastic user experience.

![](https://github.com/victorvoid/placeload.js/blob/master/placeload-desc.jpg)

Getting started
------------

Compiled and production-ready code can be found in the dist directory. The lib directory contains development code.

Install placeload.js with npm:

```sh
$ npm install placeload.js
```

Install placeload.js with bower:

```sh
$ bower install https://github.com/victorvoid/placeload.js.git
```

### 1. Include placeload on your site.

```html
<script src="dist/placeload.min.js"></script>
```

### 2. Paint your placeholder

```js

import Placeload from 'placeload.js'

Placeload
  .$('.user-placeload')
  .config({speed: '2s'})
  .line((element) => element.width(300).height(200))
  .fold(
    (err) => console.log('error: ', err),
    (allElements) => console.log('allElements: ', allElements)
  )
```

### 3. Placeload uses lazy evaluation, in that nothing is evaluated until necessary. 

```js

import Placeload from 'placeload.js'

const userLoader = Placeload
    .$('.user-placeload')
    .config({speed: '2s'})
    .line((element) => element.width(300).height(200))
    .config({spaceBetween: '30px'})
    .line((element) => element.width(400).height(20))
    .config({spaceBetween: '30px'})
    .line((element) => element.width(400).height(20))
    .config({spaceBetween: '30px'})
    .line((element) => element.width(250).height(20))

//running
userLoader.fold(
  (err) => console.log('error: ', err),
  (allElements) => console.log('allElements: ', allElements)
)

//Removing when data are loaded
API.getUsers()
  .then(users => {
      userLoader.remove()
    }
  )
```

![](https://github.com/victorvoid/placeload.js/blob/master/docs/imgs/placeload_example.gif)

- [Examples here](https://github.com/victorvoid/placeload.js/tree/master/examples)


Placeload 0.0.1 (OLD API) :see_no_evil:
--------

[Read the reference documentation for this version here](https://victorvoid.github.io/placeload.js/#documentation)

```sh
$ npm install placeload.js@0.0.1
```

```js
  var placeUserUI = new Placeload('.user-placeload');
  placeUserUI.draw({
    width: '300px',
    height: '200px'
  });

  placeUserUI.draw({
    width: '400px',
    height: '20px',
    marginTop: '10px'
  });

  placeUserUI.draw({
    width: '400px',
    height: '20px',
    marginTop: '10px'
  });

  placeUserUI.draw({
    width: '250px',
    height: '20px',
    marginTop: '10px'
  });
```

Authors
--------
The repo is written and maintained by [Victor Igor](https://github.com/victorvoid). Other contributors that have submitted  something, in alphabetical order:

- [Raniel Oliveira](https://github.com/raniel182) - UX

License
-------

The code is available under the [MIT License](LICENSE.md).

[npm-image]: https://badge.fury.io/js/placeload.js.svg
[npm-url]: https://npmjs.org/package/placeload.js
