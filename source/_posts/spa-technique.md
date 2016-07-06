---
title: 构建移动端SPA应用技术栈
date: 2016-07-05 15:58:40
tags:
    - summary
---

### 自动化构建工具
推荐gulp或者webpack，整个构建的过程可以参考我写的一个小工具[z-deploy](https://github.com/joneszhuchinagd/z-deploy)

常用的npm包：

 * babel-preset-es2015
 * babelify
 * browser-sync
 * browserify
 * del
 * gulp
 * gulp-sass
 * gulp-uglify
 * watchify


### front-end
罗列一些开发中可能需要用到的技术点：

* es6
* browserify
* sass / less
* 可伸缩框属性（Flexible Box） **注意：使用W3C标准，最新的标准会出现兼容性问题**

	```
	//example
@mixin display_flex($bo:vertical,$ba:center,$bp:center) {
  /*旧版*/
  display: -webkit-box;
  box-orient: $bo;
  -webkit-box-orient: $bo;
  /*主轴的排列*/
  box-align: $ba;
  -webkit-box-align: $ba;
  /*副轴的排列*/
  box-pack: $bp;
  -webkit-box-pack: $bp;

  ///*新版*/
  //display: flex;
  //display: -webkit-flex;
  //flex-direction: column;
  //align-items: center;
  //-webkit-justify-content: center;
  //-webkit-align-content: center;
}

	```
* 理解移动端的viewport属性

	```
	//example
	<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
	```
* 探索移动端中font-size的适配方案 （rem）
* 了解CSS3中的一些常用的动画属性 （animate）
* 尝试做一些移动端中的全屏适配，所谓的全屏适配效果跟手机中的APP类似，兼容主流的屏幕比例（有些屏幕的比例可能会更趋向于正方形，这中情况适配起来就会有很多问题可以探讨）。
* 移动端中应该尽量少用background-image，转而用img标签显示图片，因为使用img标签的图片可以保持图片本身的宽高比例。


### back-end
开发中可能会遇到一些需要后端实现的功能，譬如排行榜，记录表单，转发助力等功能。

* 掌握一门后端语言nodejs/php，编写基本的业务逻辑，以及最简单的路由功能。
	* 如果你使用的是nodejs，可能需要掌握以下常用的npm包，以及掌握es6里面基本的异步代码的写法，防止回调嵌套
		* express
		* mysql
		* co (yield + promise)
		* pm2
		* request
	* 如果你使用的是php，可以瞎JB搞，因为它是世界上最“好”的语言
* mysql数据库的建表建库，增删改查。
* 掌握基本的linux命令。

### 关于微信
在移动端开发中，用户平台经常是微信，所以有必要掌握一些微信中常用的jssdk，理解其中的原理即可，一般使用会有现成的代码。

* [网页授权获取用户基本信息](http://mp.weixin.qq.com/wiki/4/9ac2e7b1f1d22e9e57260f6553822520.html) , 一般用来获取微信用户的个人信息，openid，判断是否已经关注微信公众号等。
* [微信jssdk](http://mp.weixin.qq.com/wiki/11/74ad127cc054f6b80759c40f77ec03db.html#JSSDK.E4.BD.BF.E7.94.A8.E6.AD.A5.E9.AA.A4) , 一般用来设置分享文案以及图片。

### 关于IDE
建议使用IDEA，虽然体积比较大，但是涵盖了大部分开发中需要用到的功能。
喜欢体积小的可以考虑vscode、sublime，只是功能没有那么强大。


