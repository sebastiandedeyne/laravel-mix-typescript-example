# Laravel Mix TypeScript Example

A minimal example project on how to get started with Laravel Mix and TypeScript.

🔗 Blog post with detailed explanation: https://sebastiandedeyne.com/posts/2017/typescript-with-laravel-mix

## Adding TypeScript Support to Laravel Mix

1. Install dependencies: `yarn add typescript ts-loader` (see [`package.json`](https://github.com/sebastiandedeyne/laravel-mix-webpack-example/blob/master/package.json))
2. Create a `tsconfig.json`, or generate one with `node_modules/.bin/tsc --init` (see [`tsconfig.json`](https://github.com/sebastiandedeyne/laravel-mix-webpack-example/blob/master/tsconfig.json))
3. Add `ts-loader` and register TypeScript file extensions in `webpack.mix.config` (see below snippet or [`webpack.mix.js`](https://github.com/sebastiandedeyne/laravel-mix-webpack-example/blob/master/webpack.mix.js))

```js
mix.webpackConfig({
       module: {
           rules: [
               {
                   test: /\.tsx?$/,
                   loader: 'ts-loader',
                   exclude: /node_modules/,
               },
           ],
       },
       resolve: {
           extensions: ['*', '.js', '.jsx', '.vue', '.ts', '.tsx'],
       },
   });
```

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
