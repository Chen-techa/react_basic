# React全家桶

## React简介

### 1.是什么？

React是用于构建用户界面的JavaScript库

界面->视图（关注视图）

1.1 发送请求获取数据

1.2 处理数据（过滤，整理格式）

1.3 操作DOM呈现页面

是一个将数据渲染为HTML试图的开源JavaScript库

### 2.谁开发的

是由Facebook开发且开源

### 3.为什么学React

3.1 原生JavaScript操作DOM 繁琐、效率低下（`DOM-API操作UI`）`比如：计时器操作盒子变换颜色`

3.2 使用JavaScript直接操作DOM，浏览器会进行大量的`重绘重排`。

3.3原生JavaScript没有`组件化`编码方案，代码复用率低

3.3.1`组件化` ：html/css/js（一拆到底）

### 4.React的特点

4.1采用`组件化`模式、`声明式编码`,蹄盖哦就开发效率及组件复用率

4.1.1`声明式编码`:不用亲历亲为（学习语法）

4.2在React Native中可以使用React语法进行`移动端开发`

4.3使用`虚拟DOM`+优秀的 `Diffing算法`，尽量减少与真实DOM进行交互

### 5.学习React之前掌握的JavaScript的基础知识

5.1判断this的指向

5.2class（类）

5.3ES6的语法规范

5.4npm包管理器

5.5原型、原型链

5.6数组常用方法模块化

## React第一个案例Hello React

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello React</title>
</head>
<body>
    <!-- 准备一个容器 -->
    <div id="test"></div>
    <!-- 引入React核心库 -->
    <script src="../js/react.development.js"></script>
    <!-- 引入react-dome,用于支持react操作dom -->
    <script src="../js//react-dom.development.js"></script>
    <!-- 引入bable,用于将jsx转化为js -->
    <script src="../js/babel.min.js"></script>
    <!-- /*此处一定要写bable*/ -->
    <script type="text/babel"> 
        //写jsx脚本
        //创建虚拟dom
        const VDOM = <h1>Hello React</h1> /*此处一定不要写''*/
        //渲染虚拟dom到页面
        ReactDOM.render(VDOM,document.getElementById('test')) //参数1 虚拟DOM 参数2 容器
    </script>
</body>
</html>
```

![image-20211004211747503](../../AppData/Roaming/Typora/typora-user-images/image-20211004211747503.png)

## 虚拟DOM

### 虚拟DOM的两种创建方式JSX&JS

JSX更加简单的创建虚拟DOM

JSX其实就是原始创建虚拟DOM的语法糖，更加便捷

### 虚拟DOM与真实DOM

关于虚拟DOM：

​      1.本质上是Object类型的对象（一般对象）

​      2.虚拟DOM比较‘轻’,真实DOM比较‘重’：因为虚拟DOM是React内部在使用，无需真实DOM上那么多的属性

​      3.虚拟DOM最终会被React转化为真实DOM呈现在页面之上

## JSX

### JSX语法规则

1. 全称：JavaScript XML
2. React定义的一种类似于XML的JS扩展语法：JS+XML
   - XML早期用于存储和传输数据
3. 本质是：React.createElement(component，props，....children)
4. 作用：用来简化创建的虚拟DOM：

   - 写法：`var ele = <h1>Hello ReactJSX</h1>`
   - 注意：他不是字符串，也不是HTML/XML标签
   - 他最终生产的是一个JS对象

5. 标签名任意：HTML标签或其他标签

6.  JSX语法规则：

   ​      1.定义虚拟DOM不要写‘’

   ​      2.标签中混入JS表达式时要用{}

   ​      3.样式的类名指定不能使用class 需要使用className

   ​      4.内联样式要使用style={{ key:'value' }}这种形式

   ​      5.虚拟DOM必须只有一个跟标签

   ​      6.标签必须闭合

   ​      7.关于标签首字母

   ​        	1）若小写字母开头，则将该标签转为html中的同名标签，若无该标签对应的同名元素，则报错

   ​        	2）若大写字母开头，React就去渲染对应的组件，若组件没有定义，报错

### JSX的小练习

