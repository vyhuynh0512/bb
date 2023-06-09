# simple-html-index

[![stable](http://badges.github.io/stability-badges/dist/stable.svg)](http://github.com/badges/stability-badges)

A tiny through stream that returns a bare-bones HTML5 template with an optional
`<link>` and `<title>` in the head and `<script>` entry-point in the body.

## Example

In `html.js`

```js
var html = require('simple-html-index')

html({ title: 'hello', entry: 'bundle.js' })
  .pipe(process.stdout)
```

Now run `node html.js > index.html` and you would end up with a file that looks like this: (after formatting)

```html
<!doctype html>
<head>
  <title>hello</title>
  <meta charset="utf-8">
  </head>
<body>
  <script src="bundle.js"></script>
</body>
</html>
```

## Usage

[![NPM](https://nodei.co/npm/simple-html-index.png)](https://www.npmjs.com/package/simple-html-index)

#### `stream = html([opt])`

Returns a through stream that writes a bare-bones HTML template, with the following optional features:

- `title` whether to include a `<title>` element
- `entry` if specified, will add a `<script src={{entry}}>` element
- `css` if specified will add a `<link rel="stylesheet" href={{css}}>` element

## CLI

You can also use this from the command line to create a simple HTML index file.

```sh
# install it first
npm install simple-html-index -g

# then use it
simple-html-index -e bundle.js > index.html
```

## License

MIT, see [LICENSE.md](http://github.com/mattdesl/simple-html-index/blob/master/LICENSE.md) for details.
