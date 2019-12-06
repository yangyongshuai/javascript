1. 全局装 yarn :(npm i yarn -g)  
2. 全局装 webpack-cil webpack: (npm i webpack-cli webpack@3.9.0 -g)
3. 全局装 webpack-dev-server : ( npm i webpack-dev-server@2.9.0 -g )    //热更新
4. 局部初始化包清单:(yarn init -y)
5. 局部安装开发依赖: yarn add webpack@3.9.0 webpack-dev-server@2.9.0 html-webpack-plugin style-loader css-loader less less-loader file-loader url-loader babel babel-core babel-loader@7.1.5 babel-plugin-transform-runtime babel-preset-es2015 babel-preset-stage-0 vue-loader vue-template-compiler -D
6. 安装vue: (yarn add vue vue-router -S)
7. 创建webpack.config.js 配置
```js
const path = require('path');   //path来解决相对路径转绝对路径的问题
const htmlWebpackPlugin = require('html-webpack-plugin');
const vueLoaderPlugin = require('vue-loader/lib/plugin');

module.exports={
	 //程序入口配置项 
	entry:path.resolve('./src/main.js'), 
	// 配置构建后结果目录可以理解为出口
	output:{
		path:path.resolve('./dist'),
		filename:'build.js',
	},
	 //webpack解析不同文件数据的模块配置项
	module:{
		rules:[
			//css文件的解析处理,需要安装style-loader和css-loader
			//css-loader主要是处理css文件的，style-loader主要处理css文件里的样式的
			{
				test:/\.css$/,
				use:['style-loader','css-loader'],
			},
			//less的处理模块，需要先安装style-loader、css-loader、less、less-loader	
			{
				test:/\.less$/,
				use:['style-loader','css-loader',{
					loader:'less-loader',
					options:{
						javascriptEnabled:true,
					},
				}]
			},
			//处理图片文件的模块，需要安装file-loader、url-loader
			{
				test:/\.(jpg|jpeg|bmp|gif|png)$/,
				use:[{
					loader:'url-loader',
					options:{
						limit:102400,  //字节100KB = 102400B 具体看公司要求
						//[name]表示使用文件原名称，[ext]表示保留文件的原扩展名
						name:'assets/images/[name].[ext]'
					}
				}],
			},
			// 处理字体图标文件的模块，需要安装file-loader、url-loader
			{
				test: /\.(woff|woff2|eot|svg)$/,
				use: [{
					loader: 'url-loader',
					options: {
						limit: 102400,
						name: 'icon-font/[name].[ext]',
					},
				}],	
			},
			// js模块的处理，解析js需要借助于一个第三方的转化架包，叫babel(巴别尔)
			//需要安装：babel、babel-core、babel-loader、babel-plugin-transform-runtime、babel-preset-env、babel-preset-stage-0
			/*
				babel和babel-core是babel框架核心转换语法
				babel-loader是webpack的，这个loader可以自动去调用babel和babel，需要安装@7.1.5版本的loader
				babel-plugin-transform-runtime：处理es高级语法的核心babel插件
				babel-preset-env：处理es6关键词的预设置项，也可以考虑装babel-preset-es2015，其实就是babel-preset-env，这俩包的作用一样，选择其中一个装就行了
				babel-preset-stage-0：处理es7,8核心关键词的预设值项
				babel-loader会去调用babel和babel-core，babel和babel-core又去调用babel-plugin和babel-preset
			*/		
			{
				test:/\.js$/,
				use:['babel-loader'],
				// node_modules里的js不需要使用babel-loader构建，所以排除出去
				exclude:/node_modules/,
			},
			//vue 模块配置  需要安装vue-loader vue-template-compiler
			{
				test:/\.vue$/,
				use:['vue-loader'],
			},
		]
	},
	// 文件后缀名配置   此文件可配置可不配置
	resolve:{
		alias:{
			"@":'./components',
		},
		extensions:['.vue','.js'],  //可以省略不写后缀名 
	},
	// html模板配置的构建处理需要安装一个webpack插件，叫html-webpack-plugin
	plugins:[
		new vueLoaderPlugin(),
		new htmlWebpackPlugin({
			//template 表示构建html的入口文件路径
			template:path.resolve('./src/index.html'),
			//filename选项是html构建后的输出结果目录
			filename:path.resolve('./dist/index.html'),
			 // 在html构建输出到dist目录后，自动将dist目录里的build.js追加到html代码中，并且追加到body代码里的最后的位置
			inject:'body',
			// 对输出到dist目录里的html进行一些压缩操作
			minify: {
				 // 移除属性的引号
				removeAttributeQuotes: true,
				// 移除所有注释
				removeComments: true,
				// 压缩css
				minifyCSS: true,
				// 移除不用的换行和空格，结果就是压缩成一行代码
				collapseWhitespace: true,
				 // 压缩js
				minifyJS: true,
		  },
		})
	],
};
```
8. 创建.babelrc 文件配置
```.babelrc
	{
	    "plugins": ["transform-runtime"],
	    "presets": [
	        "es2015",
	        "stage-0"
	    ]
	}
```

9. 修改`package.json`文件
```json
	{
	  "name": "demo01",
	  "version": "1.0.0",
	  //修改这一项
	  "scripts": {
	    "start":"webpack-dev-server --inline --hot --open --port 11111"  
		//--open 自动打开  port端口号
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
