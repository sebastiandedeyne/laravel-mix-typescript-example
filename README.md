# Laravel Mix TypeScript Example

A minimal example project on how to get started with Laravel Mix and TypeScript.

🔗 Blog post with detailed explanation: https://sebastiandedeyne.com/posts/2017/typescript-with-laravel-mix

## Adding TypeScript Support to Laravel Mix

This repository contains the result of a project that supports TypeScript. Here's the recipe for adding support to your own application.

1. Install dependencies: `yarn add typescript ts-loader` (see [`package.json`](https://github.com/sebastiandedeyne/laravel-mix-typescript-example/blob/master/package.json))
2. Create a `tsconfig.json`, or generate one with `node_modules/.bin/tsc --init` (see [`tsconfig.json`](https://github.com/sebastiandedeyne/laravel-mix-typescript-example/blob/master/tsconfig.json))
3. Add `ts-loader` and register TypeScript file extensions in `webpack.mix.config` (see below snippet or [`webpack.mix.js`](https://github.com/sebastiandedeyne/laravel-mix-typescript-example/blob/master/webpack.mix.js))
4. Set up the `appendTsSuffixTo` option if you want to use TypeScript in `.vue` files too (optional)

```js
mix.webpackConfig({
       module: {
           rules: [
               {
                   test: /\.tsx?$/,
                   loader: 'ts-loader',
                   options: { appendTsSuffixTo: [/\.vue$/] },
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
