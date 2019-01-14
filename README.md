# React-project
## 手动搭建环境
+ npm init --- 创建package.json文件

+ 创建文件index.html, App.jsx, index.js,webpack.config.js

PS: 
1. 注意需要依赖的插件： webpack，wbpack-cli, @babel/preset-env, @babel-core, babel-loader, @babel/preset-react
就可以启动一个未包含css的react工程了
2. css样式需要依赖的插件： style-loader, css-loader

webpack.config.js配置如下：
`
const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, '../dist'),
    filename: 'index.js'
  },
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          'style-loader',
          'css-loader'
        ]
      },
      {
        test: /\.jsx?$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader'
        }
      }
    ]
  },
  resolve: {
    extensions: ['.js', '.css', '.scss', 'jsx']
  },
  plugins:[
    new HtmlWebpackPlugin({
      template: 'index.html',
      filename: 'index.html'
    })
  ],
  mode: 'development'
  
}
`
## 利用脚手架搭建
`
$ npm init react-app my-app
$ cd my-app
$ npm start
`
