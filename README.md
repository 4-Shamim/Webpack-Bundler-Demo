# Webpack Bundler Demo

## Dev Dependency : ( You can install others if needed! )
* @babel/core
* @babel/preset-env
* babel-loader
* css-loader
* extract-text-webpack-plugin
* file-loader
* html-loader
* html-webpack-plugin
* mini-css-extract-plugin
* node-sass
* sass-loader
* style-loader
* webpack
* webpack-cli
* webpack-dev-server

## Dependency : ( You can install any if needed! )
Noting install for now.

## Webpack Config: 
```
const HtmlWebPackPlugin = require("html-webpack-plugin");
// const MiniCssExtractPlugin = require("mini-css-extract-plugin");
const ExtractTextPlugin = require("extract-text-webpack-plugin");

module.exports = {
  entry: "./src/index.js",
  output: {
    path: `${__dirname}/build/`,
    filename: "bundle.js"
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /(node_modules)/,
        use: [
          {
            loader: "babel-loader"
          }
        ]
      },
      {
        test: /\.html$/,
        use: [
          {
            loader: "html-loader",
            options: { minimize: false }
          }
        ]
      },
      {
        test: /\.(png|svg|jpg|gif)$/,
        use: [
          {
            loader: "file-loader",
            options: {
              name: "images/[name].[ext]"
            }
          }
        ]
      },
      {
        test: /\.scss$/,
        loader: ExtractTextPlugin.extract({
          fallback: "style-loader",
          use: ["css-loader", "sass-loader"]
        })
      }
    ]
  },
  plugins: [
    new HtmlWebPackPlugin({
      template: "./src/index.html",
      filename: "./index.html"
    }),
    // new MiniCssExtractPlugin({
    //   filename: "[name].css",
    //   chunkFilenmae: "[id].css"
    //test:
    netest:("style/[name].min.css", {
      test:
    })test:
  ],
  devtool: "source-map"
};
```

##



