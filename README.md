<div align="center">
  <img width="160" height="160"
    src="https://cdn.worldvectorlogo.com/logos/coffeescript.svg">
  <a href="https://github.com/webpack/webpack">
    <img width="200" height="200" hspace="20"
      src="https://webpack.js.org/assets/icon-square-big.svg">
  </a>
  <h1>Coffee-JSXY Loader</h1>
  <p>Loads <a href="http://github.com/helixbass/coffeescript-jsxy">CoffeeScript-JSXY</a> like JavaScript</p>
</div>

<h2 align="center">Install</h2>

```bash
npm install --save-dev coffee-jsxy-loader
```

<h2 align="center">Usage</h2>


```js
import coffee from 'coffee-jsxy-loader!./file.coffee';
```

### Configuration (recommended)


```js
import coffee from 'file.coffee';
```

**webpack.config.js**

Since CoffeeScript-JSXY outputs ES6, you probably want to pass its output
to [`babel-loader`](https://github.com/babel/babel-loader)

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.coffee$/,
        use: [ 'babel-loader', 'coffee-jsxy-loader' ]
      }
    ]
  }
}
```

<h2 align="center">Options</h2>

|Name|Default|Description|
|:--:|:-----:|:----------|
|**`literate`**|`false`|Enable CoffeeScript in Markdown (Code Blocks) e.g `file.coffee.md`|
|**`sourceMap`**|`false`|Enable/Disable Sourcemaps|

### [Literate](http://coffeescript.org/#literate)

**webpack.config.js**
```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.coffee.md$/,
        use: [
          {
            loader: 'coffee-jsxy-loader',
            options: { literate: true }
          }
        ]
      }
    ]
  }
}
```

### Sourcemaps

**webpack.config.js**
```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.coffee$/,
        use: [
          {
            loader: 'coffee-jsxy-loader',
            options: { sourceMap: true }
          }
        ]
      }
    ]
  }
}
```
