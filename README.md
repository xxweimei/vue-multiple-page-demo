# vue-multiple-page-demo （webpack）

> 官方项目生成工具vue-cli使用命令vue init webpack XXX 生成的项目是单页面应用。有些时候我们需要支持多页面，此demo就是基于官方生成的项目框架，做少量修改后实现多页面的demo

## 命令说明

``` bash
# 安装依赖
npm install

# 热更新启动  页面1地址：localhost:8080/app.html 页面2地址：localhost:8080/editor.html
npm run dev

# 打包
npm run build

```

## 与官方单页面不同之处

+ 根目录新增modulemap.json文件，定义多个页面的名字以及chunks
+ src目录下新增module文件夹，将每一个页面作为一个模块放入（模块名、模块文件夹名、入口js、模块html、模块vue文件名保持一致）
+ build/webpack.base.conf.js文件内配置的entry修改为多个
+ build/webpack.dev.conf.js文件内配置的HtmlWebpackPlugin修改为多个，chunks为modulemap.json文件内定义的
+ build/webpack.prod.conf.js文件内配置的HtmlWebpackPlugin修改为多个，chunks为modulemap.json文件内定义的
