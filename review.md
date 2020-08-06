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