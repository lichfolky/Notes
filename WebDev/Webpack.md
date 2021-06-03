### Entry

```javascript
module.exports = {
  entry: "./path/to/my/entry/file.js",
};
```

### Output

The output property tells webpack where to emit the bundles it creates and how to name these files. It defaults to `./dist/main.js`

```javascript
const path = require("path");

module.exports = {
  entry: "./path/to/my/entry/file.js",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "my-first-webpack.bundle.js",
  },
};
```

### Modules

if not javascript or JSON

```javascript
const path = require("path");

module.exports = {
  entry: "./path/to/my/entry/file.js",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "my-first-webpack.bundle.js",
  },
  module: {
    rules: [{ test: /\.txt$/, use: "raw-loader" }],
  },
};
```

### Plugins

Plugins extends webpack's capabilities, plugins can be leveraged to perform a wider range of tasks like bundle optimization, asset management and injection of environment variables.

```javascript
const HtmlWebpackPlugin = require("html-webpack-plugin"); //installed via npm
const webpack = require("webpack"); //to access built-in plugins

module.exports = {
  module: {
    rules: [{ test: /\.txt$/, use: "raw-loader" }],
  },
  plugins: [new HtmlWebpackPlugin({ template: "./src/index.html" })],
};
```

In the example above, the html-webpack-plugin generates an HTML file for your application by injecting automatically all your generated bundles.

### Mode

development, production or none

```javascript
module.exports = {
  entry: "./path/to/my/entry/file.js",
  mode: "production",
};
```

npx webpack-cli init

## CLI

### Init 

```
npx webpack-cli init
```

First, you could use cd to access the different folders automatically:
cd folder && npm start && cd ..
But there’s a more elegant solution, which is to use the --prefix flag to specify the path:
npm start --prefix path/to/your/folder