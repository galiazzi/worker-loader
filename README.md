<div align="center">
  <a href="https://github.com/webpack/webpack">
    <img width="200" height="200" src="https://webpack.js.org/assets/icon-square-big.svg">
  </a>
</div>

[![npm][npm]][npm-url]
[![node][node]][node-url]
[![size][size]][size-url]

# workers-loader

Worker loader module for webpack

This fork of [webpack-contrib/worker-loader](https://github.com/webpack-contrib/worker-loader)
add SharedWorker suport

## Requirements

This module requires a minimum of Node v6.9.0 and Webpack v4.0.0.

## Getting Started

To begin, you'll need to install `workers-loader`:

```console
$ npm install workers-loader --save-dev
```

### Inlined

```js
// App.js
import Worker from 'worker-loader?shared!./Worker.js';
```

### Config

```js
// webpack.config.js
{
  module: {
    rules: [
      {
        test: /\.worker\.js$/,
        use: { loader: 'workers-loader' }
      }
    ]
  }
}
```

```js
// App.js
import Worker from './file.worker.js';

const worker = new Worker();

worker.postMessage({ a: 1 });
worker.onmessage = function (event) {};

worker.addEventListener("message", function (event) {});
```

And run `webpack` via your preferred method.

## Options

### `shared`

Type: `Boolean`
Default: `false`

Create a SharedWorker

```js
// webpack.config.js
{
  loader: 'workers-loader'
  options: { shared: true }
}
```

## License

#### [MIT](./LICENSE)

To see more options got to [webpack-contrib/worker-loader](https://github.com/webpack-contrib/worker-loader)

[npm]: https://img.shields.io/npm/v/workers-loader.svg
[npm-url]: https://npmjs.com/package/workers-loader

[node]: https://img.shields.io/node/v/workers-loader.svg
[node-url]: https://nodejs.org

[size]: https://packagephobia.now.sh/badge?p=workers-loader
[size-url]: https://packagephobia.now.sh/result?p=workers-loader