## review
---
#### HTML+CSS
1. `HTML` 相关概念
    - `HTML`
    - `XHTML`
2. 文件的命名规则
3. `HTML` 文档结构
4. `HTML` 常用标记（标签）
5. 图片的插入
    ```html
    <img src="path" alt="the text of replace image" title="the title of image"/>
    ```
6. 扩展内容
    - `&nbsp`
    - `&gt`
    - `&lt`
7. 超链接的应用
    ```html
    <a href="链接地址" title="提示信息" target="_self或者_blank">链接文本/图片</a>
    ```   
8. `HTML` 标记的语法
    - 双标记
    - 单标记
9. 常用标签
    - `div`
    - `span`
10. 表格的作用及组成
    - 作用：显示数据
    ```html
    <table>
      <tr>
        <td></td>
        <td></td>
      </tr>
    </table>
    ```
11. 表单
    ```html
    <form name=""表单名称 method="post/get" action="提交地址">
      <input type="" value=""/>
    </form>
    ```
12. `CSS` 介绍
    - `CSS`
13. `CSS` 层叠性
    - 权重高的覆盖权重低的
14. `CSS` 样式表的创建和分类
    - 行内样式表
    - 内部样式表
    - 引用外部样式表
      - 引用写法
        ```html
        <link href="目标文件路径" rel="stylesheet" type="text/css"/>
        ```
      - 导入写法
        ```html
        <style type="text/css">
          @import url("目标文件路径及文件名全称")
        </style>
        ```
15. 样式表的作用域
16. 样式表的优先级
17. `CSS` 基本语法
    ```css
    选择器{属性：属性值}
    ```
18. `CSS` 选择器定义
    - 标签选择器
    - 类选择器
    - id 选择器
    - 通配符 *
    - 伪类选择器
    - 群组选择器
    - 包含选择器
    - 属性选择器
    ..........
19. `link` 和 `import` 导入外部样式的区别
20. 选择器权重
    - id 选择器权重 0100
    - 标签选择器权重 0001
    - class 选择器权重 0010
    - 属性选择器权重 0010
    - 伪类选择器权重 0001
    - 伪元素选择器权重 0001
    - 群组为其各自本身
    - 包含为各权重之和
    - 内联样式权重为 1000
    - 继承样式权重为 0000
21. 注释符
    ```html
    <!--html的注释-->
    ```
    ```css
    /*css的注释*/
    ```
22. `CSS` 属性组成及作用
23. `CSS` 核心属性
24. 清楚浮动法
    ```css
    .clearfix:after{
      content: '.';
      display: block;
      clear: both;
      font-size: 1px;
      height: 0px;
      overflow: hidden;
      visibility: hidden;
    }
    ```
25. 盒模型的概念和组成
    - `content`
    - `padding`
    - `border`
    - `margin`
26. 盒模型的计算
27. 文本溢出省略号设置
    ```css
    div{
      width: xxx;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }
    ```
28. `HTML` 元素分类
    - 块状元素
    - 内联元素（行内元素）
29. 元素类型转换
    - `display` 属性
30. 设置一个元素在容器中水平垂直居中（运用`vertical-align`属性）
    1. 容器（父元素）加上
        ```css
        .father-el{
          text-align: center;
        }
        ```
    2. 当前元素转化为行内块元素，并且给当前元素设置垂直居中
        ```css
        .current-el{
          display: inline-block;
          vertical-align: middle;
        }
        ```
    3. 在当前元素后面加上同级元素 `span`,并对 `span` 设置
        ```css
        span{
          vertical-align: middle;
          width: 0;
          height: 100%;
          display: inline-block;
        }
        ```
31. 置换元素/非置换元素
32. `position` 定位属性
    - `static`
    - `absolute`
    - `relative`
    - `fixed`
    - `sticky`
    - `z-index`
33. 透明属性
    - `filter: alpha(opacity=value)`
    - `opacity: .value`
    - `background: rgba(255, 255, 255, 0.5)`
34. 命名锚点链接的应用
    ```html
    <div id="anchor"></div>
    <a href="#anchor"></a>
    ```
35. 滚动字幕 `marquee` 及滚动条 `scrollbar` 的扩展
36. 让一个元素在窗口水平垂直居中的多种方法
    1. 运用上面`30`的方法，运用 `vertical-align` 属性实现
    2. 如果父子元素宽高都固定，可使子元素变为 `inline-block`类型，再让其直接用 `margin` 值偏移实现
        ```css
        .father-el{
          width: 200px;
          height: 200px;
          background-color: #fff;
          text-align: center;
        }
        .children-el{
          width: 50px;
          height: 50px;
          background-color: #000;
          display: inline-block;
          margin-top: 75px;
        }
        ```
    3. 可以用固定定位方法实现
        ```css
        div{
          width: 200px;
          height: 200px;
          background: #f00;
          position: fixed;
          left: 0;
          right: 0;
          top: 0;
          bottom: 0;
          margin: auto;
        }
        ```
    4. 可以用绝对定位配合 `margin` 属性实现
        ```css
        div{
          width: 200px;
          height: 200px;
          background: #f00;
          position: absolute;
          left: 50%;
          top: 50%;
          margin: -100px 0 0 -100px;
        }
        ```
    5. 可以用绝对定位配合 `transform` 的偏移方法 `translate` 实现
        ```css
        div{
          width: 200px;
          height: 200px;
          background: #f00;
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%)
        }
        ```
    6. 可以运用弹性布局实现
        ```css
        .container-div{
          width: 500px;
          height: 500px;
          display: flex;
          justify-content: center;
          align-items: center;
        }
        ```
37. 宽高自适应
38. 浮动元素父元素高度自适应（解决高度塌陷）
    - 万能清除浮动法
      ```css
      .clearfix:after{
        content: '.';
        clear: both;
        display: block;
        height: 0;
        font-size: 1px;
        overflow: hidden;
        visibility: hidden;
      }
      ```
39. `visibility: hidden` 和 `display: none` 的区别
40. 圣杯布局和双飞翼布局
41. `CSS Sprites` 的原理（图片整合技术）（`CSS` 精灵）
42. 图片整合的优势，应用（滑动门）
43. 五大浏览器内核
    - `Trident`
    - `Gecko`
    - `Presto`
    - `Webkit`
    - `Blink`
44. 表单高级
    - 单选 `radio`
      ```html
      <input type="radio" name="gender"/>男
      <input type="radio" name="gender" checked="checked"/>女
      ```
    - 多选 `checkbox`
      ```html
      <input type="checkbox" name="like" /> 听歌
      <input type="checkbox" name="like" /> 写代码
      ```
    - 下拉菜单
      ```html
      <select name="">
        <option>1</option>
        <option selected>2</option>
      </select>
      ```
    - 多行文本 `textarea`
    - 表单字段集 `fieldset` `legend`
    - 提示信息标签 `label`
      ```html
      <label for="pass">点我，输入密码</label>
      <input type="password" id="pass" placeholder="inset the password">
      <label>
        <input type="radio" name="sex"/><span>男</span>
      </label>
      <label>
        <input type="radio" name="sex"/><span>女</span>
      </label>
      ```
    - 表单元素
      - 上传文件框 `type="file"`
      - 图像域 `type="image"`
    - 定义选项组 `optgroup`
      ```html
      <optgroup label="组名"></optgroup>
      <select>
        <optgroup label="西安">
          <option>雁塔区</option>
          <option>灞桥区</option>
          <option>高新区</option>
        </optgroup>
      </select>
      ```
45. 表格的 `CSS` 属性
46. `CSS` 规范/ `CSS` Reset
47. `HTML5` 特点（更简单，语义化，多设备跨平台....）
48. `HTML5` 与 `HTML4` 的区别
49. `HTML5` 新增标签类型
    - 结构标签
    - 新增 `web` 应用标签
    - 表单标签及属性
    - 表单验证
50. `CSS3` 简介
    - 优雅降级
    - 渐进增强
51. `CSS3` 新增选择器
    - 属性选择器
    - 伪类选择器
    - 层级选择器
52. 浏览器兼容的前缀设置
    - `webkit` -webkit-
    - `presto` -o-
    - `gecko` -moz-
    - `trident` -ms-
53. 文本阴影 `text-shadow`
54. 盒子阴影 `box-shadow`
55. `CSS3` 新增背景设置
    - `background-image`
    - `background-size`
    - `background-origin`
    - `background-clip`
56. 边框设置
    - `border-color`
    - `border-image`
    - `border-radius`
57. 怪异盒模型 `box-sizing`
58. 伸缩布局盒模型 - `flexbox`布局
    - 主轴/侧轴
    - `display: flex`
    - 伸缩容器/伸缩项目
    - 伸缩容器属性
    - 伸缩项目属性
59. 多列布局 `columns`
60. 媒体查询 `media`
61. 响应式设计（利用媒体查询检测不同设备屏幕尺寸做处理）
62. 移动端页面布局
    - 弹性布局（100%布局，流式布局）
    - 等比缩放布局（`rem`布局）
      - `DPR` = 设备像素（物理像素）/逻辑像素
63. 移动端页面常用单位
    - `rem`
    - `VH`,`VW`
    - `flexible.js`
64. CSS3 渐变 `gradient`
    - 线性渐变 `linear-gradient`
    - 径向渐变 `radial-gradient`
    - 重复渐变 `repeating-linear-gradient`
65. 过渡 `transition`
    - `transition-property`
    - `transition-duration`
    - `transition-timing-function`
    - `transition-delay`
66. 2D转换 `transform`
    - `translate(,)`
    - `rotate()`
    - `scale(,)`
    - `skew(,)`
    - `transform-origin`
67. 3D转换属性
    - transform-style
    - rotate3d(x,y,z,deg), rotateX(), rotateY(), rotateZ()
    - translate3d(x,y,z), translateX(), translateY(), translateZ()
    - scale3d(), scaleX(), scaleY(), scaleZ()
68. CSS3 动画
    - animation
    - @keyframes
    ```css
    div{
      animation: 动画名称 动画完成时间;
    }
    @keyframes 动画名称 {
      from {background: red}
      to {background: blue}
    }
    @keyframes 动画名称 {
      0% {background: red}
      25% {background: yellow}
      50% {background: blue}
      100% {background: green}
    }
    ```
69. animation 和 transition 的区别

#### JavaScript
---
1. `JavaScript` 概述   
  `JavaScript` 是一种基于对象的，事件驱动的，跨平台的，客户端脚本语言
2. `JavaScript` 组成部分
    - `ECMAScript`(定义语法规则)
    - `DOM`(document object model)
    - `BOM`(browser object model)
3. `JS` 运行   
  从上到下，从左到右
4. `JS` 注释
    - 单行注释
      ```js
      // 单行注释
      ```
    - 多行注释
      ```js
      /* 多行注释 */
      ```
5. 变量的概念及基本运算(`variable`)
6. 变量的命名规则和关键字/保留字
    - 开头 (`字母`, `$`, `_`)
    - 其他位置 (`字母`, `$`, `_`, `数字`)
    - 不能以关键字/保留字命名
    - 命名原则 (驼峰法, 匈牙利法)
7. 变量的数据类型   
    - 基本数据类型
      - `number`
      - `string`
      - `boolean`
      - `null`
      - `undefined`
    - 引用数据类型
      - `object`
8. 运算符
    - 赋值运算符
    - 关系运算符
    - 算术运算符
    - 逻辑运算符
    - 三目运算符
    - 自增自减运算符（单目运算符）
    - () 运算符
9. 变量不同类型之间的自动转换   
  `undefined` 和 `NaN` 没有自动类型转换
10. 逻辑运算 （与`&&`， 或`||`， 非`!`）
    - 非`0`的数字全为`true`
    - 非空的字符串全为`true`
    - `undefined`, `null`, `NaN`, `0`, `""`, `false` 为 `false`
11. 自增自减运算符（单目运算符）
    - `++`, 前后的区别
    - `--`, 前后的区别
12. 三目运算
13. 运算符的优先级   
  () > 自增自减运算符（单目运算符） > 算术运算符 > 关系运算符 > 逻辑运算符 > 三目运算符 > 赋值运算符
14. `isNaN()`
15. 手动强制类型转换
    - `Number()`
    - `parseInt()`
    - `parseFloat()`
    - `toString()`
    - `Boolean()`
16. `if` 语句
17. `switch` 语句
18. `if` 和 `switch` 的区别
19. 解决 `switch` 中 `case` 的穿透 (`break`)
20. `while` 循环的使用
    - `while`
    - `do while`
    - `while` 和 `do while` 的区别
21. `for` 循环的使用
22. `break` 关键字/ `continue` 关键字
23. `for` 循环的嵌套
24. 函数
    - 概念
    - 声明
      - 关键字函数
      - 赋值函数（匿名函数）
      - 构造函数
    - 函数的好处
    - 形参和实参
    - 函数的返回值 `return`
25. 函数的递归调用
26. 函数的作用域/作用域链
27. `JS` 的解析和执行
28. 函数及变量提升
29. 事件
    - 概念
    - 种类
      - 鼠标事件
      - 键盘事件
      - 表单事件
      - 表单元素事件
      - 窗口事件
    - 作用
30. 事件三要素
    - 事件源
    - 事件
    - 事件处理程序
31. 声明对象的方式
    - 字面量对象
    - 构造函数创建对象
32. `this`
33. 数组的方法
    - 改变数组的方法
      - `push()`
      - `pop()`
      - `unshift()`
      - `shift()`
      - `splice()`
      - `reverse()`
    - 不改变数组的方法
      - `slice()`
      - `join()`
      - `concat()`
34. 堆和栈
    - 堆（引用数据类型的数据）
    - 栈（基本类型的数据以及引用数据所在堆中的地址）
35. 冒泡排序/选择排序
36. `onload` 事件
    ```js
    window.onload = function(){
      // js代码
    }
    ```
37. 数组去重
38. `sort` 排序
    - `sort()` 改变原数组
    - `sort(function(a, b){return a-b})`, `a-b` 为正交换，为负位置不变
    - `sort(function(){return Math.random()-0.5})`
39. 严格模式
40. `ES5` 新增数组方法
    - `forEach()` 没有返回值
    - `indexOf()` 可以结合 `indexOf()` 进行数组去重
    - `filter()`
    - `map()`
    - `reduce()`
41. 关键字 `instanceof`
42. 字符串对象 `String`
43. 字符串方法
    - `charAt(index)`
    - `charCodeAt(index)`
    - `String.fromCharCode(ASCII码值)`
    - `indexOf()`
    - `lastIndexOf()`
    - `substr()`
    - `substring()`
    - `split()`
    - `replace()`
    - `toLowerCase()`
    - `toUpperCase()`
    - `trim()` / `trimLeft()` / `trimRight()`
44. 数学对象 `Math`
    - `Math.floor()`
    - `Math.ceil()`
    - `Math.round()`
    - `Math.sqrt(m)`
    - `Math.pow(m,n)`
    - `Math.min()`
    - `Math.max()`
    - `Math.min.apply(null, [34, 1, 35])`
    - `Math.sin()`
    - `Math.cos()`
    - `Math.random()`
45. 日期对象 `Date`
    - 月份`+1`
    - 星期`0`代表的星期日
    - `setDate()` 该方法没有返回值
      ```js
      let d = new Date()
      d.setDate(d.getDate()+10)
      ```
46. 定时器
    - `setInterval()` / `setTimeout()`
    - `clearInterval()` / `clearTimeout()`
    - 定时器中 `this` 的指向为 `window`
47. `BOM` 模型
    - `document`
    - `history`
    - `location`
    - `screen`
    - `navigator`
    - `alert()`
    - `confirm()`
    - `prompt()`
    - `setInterval()`
    - `setTimeout()`
    - `open()`   
    ........
48. `DOM` 模型
    - 节点
     - `tagName`
     - `nodeName`
     - `nodeType`
     - `nodeValue`
    - 节点关系
      - `parentNode`
      - `childNodes`
      - `children`
      - `firstChild`
      - `lastChild`
      - `firstElementChild`
      - `lastElementChild`
    - 兄弟关系
      - `nextSibling`
      - `previousSibling`
      - `nextElementSibling`
      - `previousElementSibling`
49. 节点的动态操作（增，删，改）
    - `createElement()` / `createTextNode()`
    - `appendChild()`
    - `insertBefore()`
    - `replaceChild()`
    - `cloneNode()`
    - `removeChild()` / `remove()`
50. 文档碎片 `document.createDocumentFragment()`
51. 事件对象 `event`
52. 坐标属性
    - `pageX` / `pageY`
    - `clientX` / `clientY`
    - `offsetX` /`offsetY`
53. 事件流
    - 事件冒泡 （阻止事件冒泡的方法）
    - 事件捕获
54. 阻止事件的默认行为
55. 事件监听
    - `addEventListener()`
    - `attachEvent()`
56. `DOM` 事件的三个阶段
    - 捕获阶段
    - 目标阶段
    - 冒泡阶段
57. 事件委托（机制是利用的事件冒泡）
    - 委托给父级处理
    - `e.target` / `e.srcElement`
    - `e.target.nodeName === ""`
58. `scroll` 家族属性
    - `scrollTop`
    - `scrollLeft`
    - `document.documentElement.scrollTop = document.body.scrollTop = 300`
59. `offset` 家族属性
    - `offsetWidth` / `offsetHeight`
    - `clientWidth` / `clientHeight`
    - `offsetLeft` / `offsetTop`
    - `clientLeft` / `clientTop`
60. 正则 `RegExp`
    - `^`, `$`, `.`, `\`, `*`, `+`, `?`, `{}`, `[]`, `[^]`, `|`, `()`, `\d`, `\D`, `\w`, `\W`, `\s`, `\S`
    - `i`, `g`
    - `reg.test(str)` / `reg.exec(str)`
    - `str.search(reg)` / `str.match(reg)` / `str.replace(reg,XXX)`
61. `json` 对象
    - `JSON.parse()`
    - `JSON.stringify()`
62. `this` 指向的改变
    - `bind(this指向对象)` 改变匿名函数的this指向
    - `call()` / `apply()` 改变非匿名函数的this指向
      - `函数名.call(函数体内部this指向的对象)`
      - `函数名.apply(函数体内部this指向的对象)`
63. `ES6` 新增语法
    - `let`
    - `const`
    - `for ... of`
    - 字符串模板 `` `${}` ``
    - 箭头函数 （箭头函数不能使用 `bind()`, `apply()`, `call()`改变 `this` 指向）
    - 解构赋值
    - `Array.from()`
    - `set` 集合 / `map` 集合
      - `set` 方法： `add()`, `delete()`, `has()`, `clear()` `set`集合会自动去重
      - `map` 方法： `set(键, 值)`, `delete()`, `has()`, `get()`, `clear()`
      - 都可用 `for...of` 或 `forEach` 遍历
    - 扩展运算符（展开运算符）`...`
    - `class`
    - `Promise`   
    .........
64. 数组去重的多种方法
65. `this`
66. 对象
    - 对象和类的关系
    - 对象的创建
      - 字面量方式
      - 构造函数方式
    - 工厂模式创建对象
    - 构造函数创建对象
    - 构造函数原型对象创建方法 `prototype`
    - 混合方式创建对象
67. 面向对象中的 `new` 关键字做了什么事
68. `cookie`
    - 浏览器提供的一种机制，可由`JS`进行操作
    - 会话跟踪技术
    - `cookie` 的特性（优点， 缺点）
      - `document.cookie = "user=zs; expires="+date`
69. `HTML5` 本地存储
    - `localStorage` / `sessionStorage`
    - `localStorage.setItem(key, value)`
    - `localStorage.getItem(key)`
    - `localStorage.key(index)`
    - `localStorage.length`
    - `localStorage.clear()`
    - `loaclStorage.removeItem('key')`
70. `cookie` 和 `HTML5本地存储`的区别
71. `JSON`
    - 优势
    - `JSON`对象和`JSON`字符串之间的互转
72. `AJAX`
    - 创建 `AJAX` 对象 `var xhr = new XMLHttpRequest()`
    - 连接服务器 `xhr.open(method, url, async)`
    - 将请求发送到服务器 `xhr.send()`
    - 服务器响应情况 
      - `xhr.onreadystatechange` 
      - `xhr.readyState `
      - `xhr.status`
      - `xhr.responseText`
      - `xhr.responseXML` 
73. `get` 和 `post` 区别
74. `AJAX`跨域
    - 同源策略， 同源：域名，协议，端口均为相同
    - 几种主流的跨域解决方案
      - 通过服务端语言代理请求
      - `jsonp`跨域  
      - `CORS`跨域资源共享
      - `nginx`代理跨域
75. `Promise`
    - `resolve`
    - `reject`
    - `.then()` / `.catch()`
    - `Promise.all()`
76. `Bootstrap`
77. 闭包
    - 闭包的概念
    - 闭包的作用
78. 作用域
    - 词法作用域
    - 动态作用域
    - 作用域链
79. 垃圾回收机制
    - 标记清除
    - 引用计数
80. 原型和原型链
    - `JS` 万事万物皆对象，普通对象 / 函数对象
    - 原型 `prototype` 原型对象
    - 构造器 `constructor` 指向对象的构造函数
    - 原型指针 `__proto__` 指向创建它的构造函数的原型
    - 原型链 原型链主要是靠 `__proto__` 来维护的
81. `JS` 中常见的实现继承的方式
    - 构造函数继承（对象冒充继承）--调用父类构造函数，并改变其中的`this`
    - 原型链继承 --改变原型的指向
    - 混合继承（组合继承）--前两种结合起来
    - 拷贝继承 --将对象的成员复制一份给需要继承的对象
    - `class`实现继承
82. `Object` 的方法
    - `Object.create(obj)`
    - `Object.setPrototypeOf(obj,prototype)`
    - `Object.getPrototypeOf(obj)`
    - `Object.defineProperty(obj,prop,descriptor)` 访问器方法 `set` / `get`
    - `Object.defineProperties(obj,props)`
    - `Object.getOwnPropertyDescriptor(obj,prop)`
    - `Object.getOwnPropertyDescriptors(obj)`
    - `Object.keys()`
    - `Object.values()`
    - `Object.assign()`
    - `Object.is()`
83. `ES6`类与继承
    - `class`
    - `constructor` 方法
    - `extends` 实现继承, `super` 关键字
84. `classList` 对象
85. `jQuery`
    - 简写 `$`
    - `jQuery 选择器` 例如：`$('#id')` `$('.class')` ...
    - `jQuery DOM`
      - 创建节点
      - 插入节点
      - 删除节点
      - 替换节点
      - 复制节点
      - 常用方法
    - `jQuery 动画`
      - `slideUp()` / `slideDown()`
      - `toggle()`
      - `show()` / `hide()`
      - `fadeIn()` / `fadeOut()`
      - `animate()`
      - `stop()` / `stop(true)` / `stop(true,true)`
    - `jQuery 事件`
      - `bind()` / `unbind()`
      - `on()` / `off()`
      - `one()`
      - `hover()`
      - `toggle()`
      - 事件对象
    - 转换
    - `$` 符冲突问题
    - `$.extend()` / `$.fn.extend()`
    - `$.ajax()`
86. 设计模式
    - 工厂模式
    - 单例模式
    - 代理模式
    - 策略模式
    - 发布-订阅模式（观察者模式）
87. `ES6 module`
    - `export` / `export default` / `as`
    - `import` / `as`
88. 浏览器脚本的异步加载
    - `defer` 渲染完再执行
    - `async` 下载完就执行
89. `node.js` 特点
90. `npm` 介绍
91. 搭建 `web` 服务器
    - 加载 `http` 模块
      ```js
      var http = require('http')
      ```
    - 创建 `http` 服务
      ```js
      var server = http.createServer()
      ```
    - 服务端对象监听 `request` 请求事件，用与监听客户端请求
      ```js
      server.on('request', function(req, res){
        // .....
        res.end()
      })
      ```
    - 启动 `http` 服务，监听端口
      ```js
      server.listen(3000, function(){})
      ```
92. `node.js` 模块
    - `fs`
    - `path`
    - `url`   
    .......
93. `commonJS` 模块化规范
    - `module.export`
    - `require`
    - 与 `ES6` 模块的区别（`ES6`输出是值的引用，`commonJS`输出是值的拷贝）
94. `git`
95. `Gulp`
    - `gulp.task()`
    - `gulp.src()`
    - `pipe()`
    - `gulp.dest()`
    - `gulp.watch()`
    - `gulp常用插件`
96. `sass`
    - 变量 `$`
    - 嵌套
    - `&`
    - `@import` / `@mixin` / `@extend` / `@if` / `@for` / `@function` ....
97. `RequireJS` (`AMD` 规范的实现者之一)
    - 依赖前置
      ```js
      require(['moduleA', 'moduleB'], function(moduleA, moduleB){
        // ...
      })
      ```
    - `require.config` / `data-main`
    - `define` 定义模块
    - `require` 获取模块

