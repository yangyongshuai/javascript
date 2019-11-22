1. 全局装 yarn :(npm i yarn -g)  
2. 全局装 webpack-cil webpack@3.9.0 : (npm i webpack-cli webpack -g)
3. 全局装 webpack-dev-server : ( npm i webpack-dev-server@2.9.0 -g )
4. 局部安装开发依赖: yarn add webpack@3.9.0 webpack-dev-server@2.9.0 html-webpack-plugin style-loader css-loader less less-loader file-loader url-loader babel babel-core babel-loader@7.1.5 babel-plugin-transform-runtime babel-preset-es2015 babel-preset-stage-0 vue-loader vue-template-compiler -D
5. 安装vue: (yarn add vue vue-router -S)
6. 创建webpack.config.js 配置
```js
const path = require('path');
const htmlWebpackPlugin = require('html-webpack-plugin');
const vueLoaderPlugin = require('vue-loader/lib/plugin');

module.exports={
	entry:path.resolve('./src/main.js'),
	output:{
		path:path.resolve('./dist'),
		filename:'build.js',
	},
	module:{
		rules:[
			{
				test:/\.css$/,
				use:['style-loader','css-loader'],
			},
			{
				test:/\.less$/,
				use:['style-loader','css-loader',{
					loader:'less-loader',
					options:{
						javascriptEnabled:true,
					},
				}]
			},
			{
				test:/\.(jpg|jpeg|bmp|gif|png)$/,
				use:[{
					loader:'url-loader',
					options:{
						limit:102400,
						name:'assets/images/[name].[ext]'
					}
				}],
			},
			{
				test:/\.js$/,
				use:['babel-loader'],
				exclude:/node_modules/,
			},
			{
				test:/\.vue$/,
				use:['vue-loader'],
			},
		]
	},
	resolve:{
		alias:{
			"@":'./components',
		},
		extensions:['.vue','.js'],
	},
	plugins:[
		new vueLoaderPlugin(),
		new htmlWebpackPlugin({
			template:path.resolve('./src/index.html'),
			filename:path.resolve('./dist/index.html'),
			inject:'body',
			minify: {
				removeAttributeQuotes: true,
				removeComments: true,
				minifyCSS: true,
				collapseWhitespace: true,
				minifyJS: true,
		  },
		})
	],
};
```
7. 创建.babelrc 文件配置
```.babelrc
	{
	    "plugins": ["transform-runtime"],
	    "presets": [
	        "es2015",
	        "stage-0"
	    ]
	}
```

8. 修改`package.json`文件
```json
	{
	  "name": "demo01",
	  "version": "1.0.0",
	  //修改这一项
	  "scripts": {
	    "start":"webpack-dev-server --inline --hot --open --port 11111"
	  },
	  "license": "MIT",
	  "devDependencies": {
	    "babel": "^6.23.0",
	    "babel-core": "^6.26.3",
	    "babel-loader": "7.1.5",
	    "babel-plugin-transform-runtime": "^6.23.0",
	    "babel-preset-es2015": "^6.24.1",
	    "babel-preset-stage-0": "^6.24.1",
	    "css-loader": "^3.2.0",
	    "file-loader": "^4.3.0",
	    "html-webpack-plugin": "^3.2.0",
	    "less": "^3.10.3",
	    "less-loader": "^5.0.0",
	    "style-loader": "^1.0.0",
	    "url-loader": "^2.3.0",
	    "vue-loader": "^15.7.2",
	    "vue-template-compiler": "^2.6.10",
	    "webpack": "3.9.0",
	    "webpack-dev-server": "2.9.0"
	  },
	  "dependencies": {
	    "vue": "^2.6.10",
	    "vue-router": "^3.1.3"
	  }
	}

```


运行环境: (yarn run start)