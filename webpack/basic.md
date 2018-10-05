## CommonJS

+ 定义：一种使用广泛的js模块化规范
+ 核心思想：通过require方法来同步加载依赖的其他模块，通过module.exports导出需要暴露的接口。
+ 优点：可复用于Node.js环境下并运行，例如做同构应用；通过NPM发布的很多第三方模块都采用了CommonJS规范。
+ 缺点：这样的代码无法直接运行在浏览器环境下，必须通过工具转换成标准的 ES5。

* 例如
 ```
 // 导入
 const moduleA = require('./moduleA');
 // 导出
 module.exports = moduleA.someFunc;
 ```

## AMD
+ 定义: 也是一种js模块化规范。
+ 区别：它采用异步的方式去加载以来的模块。主要是为了解决针对浏览器环境的模块化问题，最具代表性的实现是 requirejs。
+ 优点：
    1.可再不转换代码的情况下直接在浏览器中运行；
    2.可异步加载依赖；
    3.可并行加载多个依赖；
    4.代码可运行在浏览器环境和Node.js环境下。
+ 缺点： JavaScript 运行环境没有原生支持 AMD，需要先导入实现了 AMD 的库后才能正常使用。

* 例如
 ```
    // 定义一个模块
    define('module', ['dep'], function(dep) {
      return exports;
    });
    // 导入和使用
    require(['module'], function(module) {
    });
 ```

## ES6模块化
+ 定义：也是js一种模块化规范，将取代CommonJS和AMD规范。
+ 缺点：目前无法直接运行在大部分 JavaScript 运行环境下，必须通过工具转换成标准的 ES5 后才能正常运行。
* 采用 ES6 模块化导入及导出时的代码如下:

 ```
    // 导入
    import { readFile } from 'fs';
    import React from 'react';
    // 导出
    export function hello() {};
    export default {
      // ...
    };
 ```

## 样式中的模块化
 ```
    // util.scss 文件
    
    // 定义样式片段
    @mixin center {
      // 水平竖直居中
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%,-50%);
    }
    
    // main.scss 文件
    
    // 导入和使用 util.scss 中定义的样式片段
    @import "util";
    #box{
      @include center;
    }
 ```
## Babel插件
> 支持把任何新语法转换成ES5的写法。