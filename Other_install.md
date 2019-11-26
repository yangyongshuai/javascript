### 注意: 安装全局包时必须要用`npm`来装, 千万别用`yarn`

### 全局安装 `node-js`
1. 安装网址:`(https://nodejs.org/en/download/)`
2. 安装`node-js`
3. 安装完成查看版本`node -v`

### 全局安装淘宝镜像源
1. 安装淘宝镜像源 (`npm install -g cnpm --registry=https://registry.npm.taobao.org`)  安装过后所有`npm`前面加`c`使用
2. 查看镜像源`cnpm -v`

### 全局安装`webpack`
1. 安装`webpack`: (`npm i webpack-cli webpack -g`)  最好是3.9.0的版本
	- `-g`表示安装全局资源包

### `npm`卸载安装包
1. 卸载: (`npm uninstall 包名称 -g`)

### `npm`初始化包清单
1. 局部初始化包清单:(`npm init -y`) 

### 全局安装`yarn`
1. 安装`yarn`:(`npm i yarn -g`)

### `yarn`修改淘宝镜像源
1. `yarn`淘宝镜像源: (`yarn config set registry https://registry.npm.taobao.org`)

### `yarn`初始化包清单
1. 局部初始化包清单:(`yarn init -y`)

### `yarn`安装包指令
1. 安装包指令:(`yarn add 包名称 -S 或 -D`)
	- `-S` src目录里项目需要的包 `--save`的简写 代码里要用的资源包都装-S，
	- `-D` 构建解析有关的包都装-D

### 安装`vue-cli`脚手架
1. 安装`vue-cli`:(`cnpm install vue-cli -g`) 
2. 查看版本: (`vue -v`) 
3. 创建一个文件夹安装配置文件 (`vue init webpack 文件名称`)
4. 安装配置文件夹`node_modules`: (`cnpm install`)
5. 运行网页: (`npm run dev`)

### 安装`vuex`
1. `vuex`:(`cnpm install vuex --save`)
* 指定版本号安装:
1. 版本号安装:(`cnpm install vuex @版本号`)

### 安装`react`脚手架
1. 安装`node-js`
2. 安装`npm`或者`yarn`
3. 淘宝镜像源 `npm config set registry http://registry.npm.taobao.org/`
4. 全局安装 `cnpm i create-react-app -g`
5. 局部安装创建项目文件夹 `create-react-app 文件夹名字` 
6. 进入文件夹名称的控制台  `cd 文件夹名称`
7. 启动项目 `npm start`
