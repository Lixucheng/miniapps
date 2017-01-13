# miniapps

小程序项目脚手架工具

## 如何安装

> npm i miniapps -g

依赖: [Node.js](https://nodejs.org/en/) and [Git](https://git-scm.com/).

## 功能

> miniapp -h

<img src="http://static.galileo.xiaojukeji.com/static/tms/shield/miniapp_help.jpeg" />

### 创建小程序项目

执行 init 命令后，可以看到 <project-name> 目录中生成 `src` 和 `dist` 两个文件夹，其中 `src` 为源码目录，`dist`目录为编译 `src` 后生成的目录。dist 目录可用来在小程序开发者工具中打开。

``` bash
$ miniapp init <project-name>
```

Example:

``` bash
$ miniapp init miniapp-demo
```

### 编译

首先，先进入执行初始化命令时指定的目录，然后执行 `miniapp build` 对 `src`目录内的文件进行编译。miniapp 会根据文件后缀自动进行相应编译，目前支持 `sass -> wxss`，`stylus-wxss`，`ES6 -> ES5` 的编译，编译后的文件在 `dist` 目录中。

``` bash
$ cd miniapp-demo
$ miniapp build
```

### 监视文件改动

`--watch`，`-w` 选项可以让我们在文件发生改动时自动重新编译。

``` bash
$ cd miniapp-demo
$ miniapp build -w
```

### 快速生成 page 目录:

该命令可以快速生成符合微信小程序官方规范的目录结构，并且将新页面自动注册到 app.json 文件中

``` bash
$ miniapp gen <page_name>
```

示例:

``` bash
$ cd miniapp-demo
$ miniapp gen auth
```

以上命令执行后会自动在 `src/pages` 和 `dist/pages` 目录中生成 auth 文件夹：
```
 └─┬ src
      ├─┬ pages          
      │ ├── auth                
      │ │ ├── auth.js
      │ │ ├── auth.json
      │ │ ├── auth.wxml
      │ │ ├── auth.sass
      ...
 └─┬ dist
      ├─┬ pages          
      │ ├── auth                
      │ │ ├── auth.js
      │ │ ├── auth.json
      │ │ ├── auth.wxml
      │ │ ├── auth.wxss
      ...
```

### 安装组件:

除了使用 `miniapp gen` 来快速生成 page 结构，我们还可以使用 `miniapp install` 来从 git 安装指定页面，目前所有模块都将在 [https://github.com/miniapps-team/ ](https://github.com/miniapps-team/) 该项目下获取。

``` bash
$ miniapp i <widget_name>
```

示例:

``` bash
$ cd miniapp-demo
$ miniapp i login
```

以上命令执行后，会依次执行以下步骤：
1. 从 repo [https://github.com/miniapps-team/minapp-widget-login.git ](https://github.com/miniapps-team/minapp-widget-login.git) 下载。
2. 拷贝 `minapp-widget-login` repo 中的组件到 `src/pages` 和 `dist/pages` 下。


### 打开文档:

该命令可以通过默认浏览器打开微信小程序官方开发文档页面，方便开发者进行相关 API 查询。

``` bash
$ miniapp doc 
```


## FAQ

#### 1、可以自定义组件下载地址吗

> 可以，自己配置即可



### License

[MIT](http://opensource.org/licenses/MIT)

