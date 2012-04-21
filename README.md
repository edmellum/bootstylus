Bootstylus
=================

A port of [Twitter Bootstrap](http://twitter.github.com/bootstrap) from Less to Stylus.


Installation
------------
`$ npm install bootstylus`


JavaScript API
--------------

With a connect compatible framework, like express:
```javascript
var connect = require('connect')
  , stylus = require('stylus')
  , bootstrap = require('bootstylus');

var server = connect();

function compile(str, path) {
  return stylus(str)
    .set('filename', path)
    .set('compress', true)
    .use(nib());
}

server.use(stylus.middleware({
    src: __dirname
  , compile: compile
}));
```


Stylus API
----------
To get everything(except the responsive grid)
`@import 'bootstylus'`
Using individual parts:
`@import 'bootstylus/grid'
If you need the responsive grid:
`@import 'bootstylus/responsive'


Todo
----
- Use Nib for gradients and the like
- Get rid of Stylus warnings
- Clean up the Less to Stylus converter


Copyright and license
---------------------

Copyright 2012 Twitter, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this work except in compliance with the License.
You may obtain a copy of the License in the LICENSE file, or at:

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.