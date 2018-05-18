---
title: angual脚手架自学笔记
date: 2018-05-18 14:10:01
tags: [angular2,自学笔记]
---

项目地址：[https://github.com/SnowBeatRain/angular_my][5]

----------
本笔记用于个人学习，使用angular cli工具进行开发

##前期准备

 1. 学习官网[angular官网][1]；
 2. 配置电脑环境
    >检查电脑是否装有node，npm，并且运行node -v,npm -v 检查node npm版本是否是8.x 和5.x以上。
然后全局安装angular cli：`npm install -g @angular/cli`
 3. 创建项目
    > 运行命令：`ng mew my-app`
 4. 运行项目
 > `cd my-app`
`ng serve --open`
 5. 自行学习项目目录（[angular官网][2]）


##项目实战开发

 1. 参考[angular官网][3]中的英雄项目  (不做描述)
 >组件，路由，服务，http

 2. 根据自己以往的项目进行实际开发（主要记录一下当时没有立即写出来的部分）

首先去看来看官网的例子，然后针对自己以往的vue项目进行angular改造：
（本人使用的编辑器是vs code,安装了**Angular Files**插件，这样在创建组件 路由 服务的时候可以不通过命令行进行，而是直接右键创建对应的文件）

 - 创建组件
    >运行：ng generate component <name>
    或者直接右键创建，简单暴力（前提是安装了上述插件）
 - 使用路由，设置底部导航
 >1、在app.component.html 中创建底部导航，外层设置一个开关用于控制底部导航条的显示隐藏。
如图所示
![底部导航图][4]
2、创建路由文件：并配置路由。（前提是已经创建过路由路径下的文件）
在app.router.module.ts文件中首先导入路由
// 导入路由
`import { RouterModule, Routes } from '@angular/router';`
// 导入路由下的组件,例如:
`import { HomeComponent } from './home/home.component';`
`import { MineComponent } from './mine/mine.component';`
`import { HomelistComponent } from './homelist/homelist.component';`
`import { PasscodeComponent } from './passcode/passcode.component';`
// 设置路由规则
`const routes: Routes = [`
  `{
     `// 由于设置了base href（在index.html的head中），所以路径前不用再加/`
     ` path: 'home',`
    `component: HomeComponent,`
    `data: { title: '包裹' }`
  `},
3、路由文件下的NgModule({})中必须设置以下内容：
`imports: [RouterModule.forRoot(routes)],`
`exports: [ RouterModule ]`

  [1]: https://www.angular.cn/
  [2]: https://www.angular.cn/
  [3]: https://www.angular.cn/
  [4]: https://raw.githubusercontent.com/SnowBeatRain/blogImages/master/angluar_nav.png
  [5]:https://github.com/SnowBeatRain/angular_my