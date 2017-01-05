# nymag-handlebars

[![Build Status](https://travis-ci.org/nymag/nymag-handlebars.svg)](https://travis-ci.org/nymag/nymag-handlebars)
[![Code Climate](https://codeclimate.com/github/nymag/nymag-handlebars/badges/gpa.svg)](https://codeclimate.com/github/nymag/nymag-handlebars)

A collection of helpers and partials for handlebars

# Installation

```
npm install --save nymag-handlebars
```

# Usage

By default, `nymag-handlebars` will export a function that returns a new handlebars instance with all of the helpers and partials added.

```js
var hbs = require('nymag-handlebars')(),
  template = hbs.compile('<h1>Hello {{ place }}!</h1>'),
  result = template({ place: 'World' });

// result: <h1>Hello World!</h1>
```

## Passing env in

If you want to configure and use your own handlebars environment, you can pass it through

```js
var Handlebars = require('express-handlebars'),
  env = new Handlebars({ /* some config */ }),
  hbs = require('nymag-handlebars')(env),
  app = require('express')();

app.engine('handlebars', hbs.engine);
app.set('view engine', 'handlebars');
```