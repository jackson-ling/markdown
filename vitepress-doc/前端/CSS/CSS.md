---
sidebar: false
aside: left
outline: [2, 4]
---

<h1 style="text-align: center; font-weight: bold;">基于 Javaweb 课程的 CSS 笔记</h1>

---

## 基本介绍

> <h3>CSS <span style = "color:red;font-weight:bold">层叠样式表</span>(英文全称：(Cascading Style Sheets)) 能够对网页中元素位置的排版进行像素级精确控制，支持几乎所有的字体字号样式，拥有对网页对象和模型样式编辑的能力 ,简单来说,美化页面</h3>

## 引入方式

### 行内式

> <h3><span style = "color:red;font-weight:bold">常配合JS使用</span></h3>
> <h3>语法： `style="样式名: 样式值; 样式名: 样式值; ..."</h3>
>
> <h3>缺点如下</h3>
>
> <h3>1. 代码<span style = "color:red;font-weight:bold">复用性低</span>，不利于维护</h3>
>
> <h3>2. css 样式代码和 html 结构代码紧在一起，<span style = "color:red;font-weight:bold">影响阅读</span>，影响文件大小，<span style = "color:red;font-weight:bold">影响性能</span></h3>

```html
<input
  type="button"
  value="按钮"
  style="
            width: 60px;    /* 宽度 */
            height: 40px;  /* 高度 */
            background-color: rgb(140, 235, 100);  /* 背景色 */
            color: white;   /* 字体颜色 */
            border: 3px solid green;   /* 边框线：实线（solid） */
            font-size: 22px;  /* 字体大小 */
            font-family: '隶书';  /* 字体样式 */
            border-radius: 5px;   /* 边角弧度 */
    "
/>
```

### 内嵌式

> <h3>说明</h3>

> - **内嵌式样式需要<span style = "color:red;font-weight:bold">在 head 标签</span>中,使用<span style = "color:red;font-weight:bold">一对 style 标签</span>，通过<span style = "color:red;font-weight:bold">指定标签</span>的方式来<span style = "color:red;font-weight:bold">定义 CSS 样式</span>（缺点：无法精确控制，只能全局改变）**
> - **CSS 样式的<span style = "color:red;font-weight:bold">作用范围</span>控制要<span style = "color:red;font-weight:bold">依赖选择器</span>**
> - **CSS 的样式代码中注释的方式为 /\* \*/**
> - **内嵌式虽然对样式代码做了抽取,但是 CSS 代码仍然在 html 文件中**
> - **内嵌样式<span style = "color:red;font-weight:bold">仅仅能作用于当前文件</span>,代码<span style = "color:red;font-weight:bold">复用度还是不够</span>,不利于网站风格统一**

```html
<head>
  <meta charset="UTF-8" />
  <style>
    /* 通过选择器确定样式的作用范围 */
    input {
      width: 60px; /* 宽度 */
      height: 40px; /* 高度 */
      background-color: rgb(140, 235, 100); /* 背景色 */
      color: white; /* 字体颜色 */
      border: 3px solid green; /* 边框线：实线（solid） */
      font-size: 22px; /* 字体大小 */
      font-family: "隶书"; /* 字体样式 */
      border-radius: 5px; /* 边角弧度 */
    }
  </style>
</head>
<body>
  <input type="button" value="按钮1" />
  <input type="button" value="按钮2" />
  <input type="button" value="按钮3" />
  <input type="button" value="按钮4" />
</body>
```

### 外部样式表

**说明**

> - **CSS 样式代码从 html 文件中剥离,利于代码的维护**
> - **CSS 样式文件可以被多个不同的 html 引入,利于网站风格统一**
> - **将 css 代码单独放入一个 `.css` 文件中，通过<span style = "color:red;font-weight:bold">&lt;link&gt;标签</span>从外部引入 CSS 样式表，<span style = "color:red;font-weight:bold;font-size:20px">&lt;link href="CSS 文件路径" rel="stylesheet" /&gt;</span>，rel 后填写的是文件类型，CSS 指定是 stylesheet**

```html
<head>
  <meta charset="UTF-8" />
  <!--引入外部样式表-->
  <link href="CSS文件路径" rel="stylesheet" />
</head>
<body>
  <!--主体内容-->
</body>
```

### 常见样式属性 ⭐

## 选择器

### 元素选择器

> <h3>说明</h3>

> - **语法：<span style = "color:red;font-weight:bold;font-size:20px">元素名{}</span>**
> - **引入方式：在 <span style = "color:red;font-weight:bold">head 标签</span>中，使用<span style = "color:red;font-weight:bold">一对 style 标签</span>，通过<span style = "color:red;font-weight:bold">指定标签</span>的方式来<span style = "color:red;font-weight:bold">定义 CSS 样式</span>**
> - **根据标签名确定样式的作用范围**
> - **样式只能作用到同名标签上,其他标签不可用**
> - **相同的标签未必需要相同的样式,会造成样式的作用范围太大**

```html
<head>
  <meta charset="UTF-8" />
  <style>
    input {
      width: 60px; /* 宽度 */
      height: 40px; /* 高度 */
      background-color: rgb(140, 235, 100); /* 背景色 */
      color: white; /* 字体颜色 */
      border: 3px solid green; /* 边框线：实线（solid） */
      font-size: 22px; /* 字体大小 */
      font-family: "隶书"; /* 字体样式 */
      border-radius: 5px; /* 边角弧度 */
    }
  </style>
</head>
<body>
  <input type="button" value="按钮1" />
  <input type="button" value="按钮2" />
  <input type="button" value="按钮3" />
  <input type="button" value="按钮4" />
  <button>按钮5</button>
</body>
```

### id 选择器

> <h3>说明</h3>

> - **语法：<span style = "color:red;font-weight:bold;font-size:20px">#（id 值） {}</span>**
> - **定义方式：在 <span style = "color:red;font-weight:bold">head 标签</span>中，使用<span style = "color:red;font-weight:bold">一对 style 标签</span>，通过<span style = "color:red;font-weight:bold">指定标签</span>的方式来<span style = "color:red;font-weight:bold">定义 CSS 样式</span>**
> - **引入方式：添加属性 id="id 值"**
> - **根据元素 id 属性的值确定样式的作用范围**
> - **id 属性的值在页面上具有<span style = "color:red;font-weight:bold">唯一性</span>,所有 id 选择器也<span style = "color:red;font-weight:bold">只能影响一个元素</span>的样式**
> - **因为 id 属性值不够灵活,所以使用该选择器的情况较少**

```html
<head>
  <meta charset="UTF-8" />
  <style>
    #btn1 {
      width: 60px; /* 宽度 */
      height: 40px; /* 高度 */
      background-color: rgb(140, 235, 100); /* 背景色 */
      color: white; /* 字体颜色 */
      border: 3px solid green; /* 边框线：实线（solid） */
      font-size: 22px; /* 字体大小 */
      font-family: "隶书"; /* 字体样式 */
      border-radius: 5px; /* 边角弧度 */
    }
  </style>
</head>
<body>
  <input id="btn1" type="button" value="按钮1" />
  <input id="btn2" type="button" value="按钮2" />
  <input id="btn3" type="button" value="按钮3" />
  <input id="btn4" type="button" value="按钮4" />
  <button id="btn5">按钮5</button>
</body>
```

### class 选择器

> <h3>说明</h3>

> - **语法：<span style = "color:red;font-weight:bold;font-size:20px"> .(class 值) {}</span>**
> - **定义方式（1）在 <span style = "color:red;font-weight:bold">head 标签</span>中，使用<span style = "color:red;font-weight:bold">一对 style 标签</span>，通过<span style = "color:red;font-weight:bold">指定标签</span>的方式来<span style = "color:red;font-weight:bold">定义 CSS 样式</span>（2）还可以写在 CSS 文件中，在 html 标签中通过<span style = "color:red;font-weight:bold">&lt;link&gt;标签</span>从外部引入 CSS 样式表，**
> - **引入方式：添加属性 class="class 值 1 class 值 2 class 值 3..."，使用<span style = "color:red;font-weight:bold">多个 class 值时，用空格隔开</span>**
> - **根据元素 class 属性的值确定样式的作用范围**
> - **class 属性值<span style = "color:red;font-weight:bold">可以有一个,也可以有多个</span>,多个不同的标签也<span style = "color:red;font-weight:bold">可以是使用相同的 class 值</span>**
> - **多个选择器的<span style = "color:red;font-weight:bold">样式</span>可以在同一个元素上进行<span style = "color:red;font-weight:bold">叠加</span>**
> - **因为 class 选择器非常灵活,所以在 CSS 中,使用该选择器的情况较多**

```html
<head>
  <meta charset="UTF-8" />
  <style>
    .shapeClass {
      display: block;
      width: 80px;
      height: 40px;
      border-radius: 5px;
    }
    .colorClass {
      background-color: rgb(140, 235, 100);
      color: white;
      border: 3px solid green;
    }
    .fontClass {
      font-size: 22px;
      font-family: "隶书";
      line-height: 30px;
    }
  </style>
</head>
<body>
  <input class="shapeClass colorClass fontClass" type="button" value="按钮1" />
</body>
```
