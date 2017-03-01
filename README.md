## 快速构建React+Webpack+ES6项目

之前vue的学习中使用Vue-cli 可以快速创建vue项目，所以在学习React的时候我就在想有没有类似于cli的脚手架可以帮助我们快速构建React项目。然后我就找到了...很多！官方有一个cerate-react-app被吐槽不好用，还有基于Vue-cli的React Demo https://github.com/kenberkeley/react-demo 。

更多则是基于Yeoman的，这里找到两个不错的脚手架，分别是generator-reactpackage和generator-react-webpack。前者适合小型项目，默认使用sass，支持es6。后者功能更为完善，部署时提供css，sass，less选项，支持es6，适合大中型项目。

顺带提一下找到的一个不错的模板：http://react-china.org/t/react-antd-es6-echarts-webpack-yarn/10348/6，虽然作者说是脚手架，但个人感觉更像一个模板，也是十分不错的。

这里就以generator-reactpackage为例简要介绍一下React脚手架配置。

> 有兴趣自己开发脚手架的可以移步：http://www.cnblogs.com/jarson-7426/archive/2016/09/04/5839243.html ，这篇博客对yeoman开发脚手架做了详细的介绍。

废话不多说，直接上手。

#### 检查Node.js版本为最新

这里不多说，不知道怎么升级的参照：http://www.jb51.net/article/52409.htm，或者干脆直接去官网下载最新版本覆盖安装。

#### 替换npm源为淘宝源

```
npm config set registry “https://registry.npm.taobao.org”
```

之前的开发中多是使用cnpm，后来实际上手中发现generator-reactpackage在创建好项目后会自动执行`npm install`去安装依赖，如果不事先将npm源替换为淘宝源，因为和谐的问题，install的过程会巨慢而且易出错。

#### 安装脚手架

因为这个脚手架是使用yeoman开发，所以需要先安装yeoman，这里使用全局安装：

```
npm install -g yo
```

然后安装脚手架，依然是全局安装：

```
npm install -g generator-reactpackage
```

#### 创建React项目

先在工作目录新建项目文件夹，使用命令行定位到该文件夹下，键入：

```
yo reactpackage
```

随后reactpackage会在改目录中创建项目所需文件，完成后显示：I'm all done.字样并自动执行npm install && bower install去安装项目中的依赖。安装完成后键入：

```
npm run dev
```

项目即开始自动处理，手动打开浏览器输入：loaclhost:8888即可看到页面，支持热加载。

如果想在启动项目后自动打开浏览器，可以参照这个：http://blog.csdn.net/isaisai/article/details/54892888





#### 