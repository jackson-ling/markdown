---
sidebar: false
aside: left
outline: [2, 3]
---

<h1 style="text-align: center; font-weight: bold;">基于 Javaweb 课程的 JavaScript 笔记</h1>

---

## 基本介绍

### 历史

> #### Javascript 是一种由 Netscape(网景)的 LiveScript 发展而来的原型化继承的面向对象的动态类型的区分大小写的<span style="color:red;font-weight:bold">客户端脚本语言</span>，主要<span style="color:red;font-weight:bold">目的是为了解决服务器端语言，遗留的速度问题</span>，为客户提供更流畅的浏览效果。当时服务端需要对数据进行验证，由于网络速度相当缓慢,只有 28.8kbps，验证步骤浪费的时间太多。于是 Netscape 的浏览器 Navigator 加入了 Javascript，提供了数据验证的基本功能。<span style="color:red;font-weight:bold">ECMA-262 是正式的 JavaScript 标准</span>。这个标准基于 JavaScript (Netscape) 和 JScript (Microsoft)。ECMA-262 的开发始于 1996 年，在 1997 年 7 月，ECMA 会员大会采纳了它的首个版本。这个标准由 ECMA 组织发展和维护。JavaScript 的正式名称是 "ECMAScript"。<span style="color:blue;font-weight:bold">JavaScript 的组成包含 ECMAScript、DOM、BOM</span>。<span style="color:red;font-weight:bold">JS 是一种运行于浏览器端上的小脚本语句,可以实现网页如文本内容动,数据动态变化和动画特效等</span>

### 特点

#### （1）脚本语言

> #### JavaScript 是一种<span style="color:red;font-weight:bold">解释型的脚本语言</span>。不同于 C、C--、Java 等语言先编译后执行, JavaScript 不会产生编译出来的字节码文件，而是在程序的<span style="color:red;font-weight:bold">运行过程中对源文件逐行进行解释</span>

#### （2）基于对象

> #### JavaScript 是一种基于对象的脚本语言，它不仅可以创建对象，也能使用现有的对象。但是面向对象的三大特性：『封装』、『继承』、『多态』中，JavaScript <span style="color:red;font-weight:bold">能够实现封装，可以模拟继承</span>，<span style="color:blue;font-weight:bold">不支持多态</span>，所以它<span style="color:red;font-weight:bold">不是</span>一门<span style="color:red;font-weight:bold">面向对象</span>的编程语言

#### （3）弱类型

> #### JavaScript 中也有明确的数据类型，但是声明一个<span style="color:red;font-weight:bold">变量</span>后它<span style="color:red;font-weight:bold">可以接收任何类型的数据</span>，并且会在程序执行过程中<span style="color:red;font-weight:bold">根据上下文自动转换类型</span>

#### （4）事件驱动

> #### JavaScript 是一种采用事件驱动的脚本语言，它不需要经过 Web 服务器就可以对用户的输入做出响应

#### （5）跨平台性

> #### JavaScript 脚本语言<span style="color:red;font-weight:bold">不依赖于操作系统，仅需要浏览器的支持</span>。因此一个 JavaScript 脚本在编写后可以带到任意机器上使用，前提是机器上的浏览器支持 JavaScript 脚本语言。目前 JavaScript 已被大多数的浏览器所支持

### ECMA 及版本变化

- 是一种由欧洲计算机制造商协会（ECMA）通过 ECMA-262 标准化的脚本程序语言,ECMAScript 描述了语法、类型、语句、关键字、保留字、运算符和对象。它就是定义了脚本语言的所有属性、方法和对象。

- ECMA-262 第 1 版本质上跟网景的 JavaScript 1.1 相同，删除了浏览器特定代码和少量细微的修改.ECMA-262 要求支持 Unicode 标准（以支持多语言）且对象要与平台无关
- ECMA-262 第 2 版只是做了一些编校工作，主要是为了严格符合 ISO/IEC-16262 的要求，并没有增减或改变任何特性。

- ECMA-262 第 3 版第一次真正对 ECMAScript 进行更新，更新了字符串处理、错误定义和数值输出，增加了对正则表达式、新的控制语句、try/catch 异常处理的支持。
- ECMA-262 第 4 版是对这门语言的一次彻底修订。开发者开始修订 ECMAScript 以满足全球 Web 开发日益增长的需求。 第 4 版包括强类型变量、新语句和数据结构、真正的类和经典的继承，以及操作数据的新手段。
- ECMA-262 第 5 版是 ECMA-262 第 3 版的小幅改进，于 2009 年 12 月 3 日正式发布。第 5 版致力于厘清第 3 版存在的歧义，也增加了新功能。新功能包括原生的解析和序列化 JSON 数据的 JSON 对象、方便继承和高级属性定义的方法、新的增强 ECMAScript 引擎解释和执行代码能力的严格模式。
- ECMA-262 第 6 版俗称 <span style="color:red;font-weight:bold">ES6</span>、ES2015 或 ES Harmony（和谐版），于 2015 年 6 月发布。<span style="color:red;font-weight:bold">这一版包含了大概这个规范有史以来最重要的一批增强特性。</span>ES6 正式支持了类、模块、迭代器、生成器、箭头函数、期约、反射、代理和众多新的数据类型。但是并不是所有的浏览器都全面支持了 ES6,很多情况下我们需要将 ES6 的语法通过工具转换成 5 以后运行
- ECMA-262 第 7 版也称为 ES7 或 ES2016，于 2016 年 6 月发布。这次修订只包含少量语法层面的增强，如 Array.prototype.includes 和指数操作符。
- ECMA-262 第 8 版也称为 ES8、ES2017，完成于 2017 年 6 月。这一版主要增加了异步函数（async/await）、SharedArrayBuffer 及 Atomics API、Object.values()/Object.entries()/Object.getOwnProperty- Descriptors()和字符串填充方法，另外明确支持对象字面量最后的逗号。
- ECMA-262 第 9 版也称为 ES9、ES2018，发布于 2018 年 6 月。这次修订包括异步迭代、剩余和扩展属性、一组新的正则表达式特性、Promise finally()以及模板字面量修订。
- ECMA-262 第 10 版也称为 ES10、ES2019，发布于 2019 年 6 月。这次修订增加了 Array.prototype.flat()/flatMap()、String.prototype.trimStart()/trimEnd()、Object.fromEntries()方法以及 Symbol.prototype.description 属性，明确定义了 Function.prototype.toString()的返回值并固定了 Array.prototype.sort()的顺序。另外，这次修订解决了与 JSON 字符串兼容的问题，并定义了 catch 子句的可选绑定。
- ECMA-262 第 11 版，也成为 ES11、ES2020，发布于 2020 年 6 月。这次修订增加了 String 的 matchAll 方法、动态导入语句 import()、import.meta、export \* as ns from 'module'、Promise.allSettled、GlobalThis、Nullish coalescing Operator、Optional Chaining 以及一种新的数据类型 BigInt，在此之后 JavaScript 正式迎来第 8 位数据类型。

## 引入方式

### 内嵌式

#### 基本介绍

> #### 在 &lt;head&gt; 标签中，使用 &lt;script&gt; &lt;/script&gt;标签引入
>
> #### 函数类型可以使用 <span style="color:red;font-weight:bold">function</span> 定义
>
> #### <span style="color:red;font-weight:bold">弹窗提示</span>函数：<span style="color:red;font-weight:bold">alert( )</span>
>
> #### 函数<span style="color:red;font-weight:bold">绑定点击行为</span>：<span style="color:red;font-weight:bold">onclick</span> 属性

#### 注意点

> #### &lt;script&gt; 标签<span style="color:red;font-weight:bold">必须是一对</span>的方式引入，否则在调用相关函数时无法生效
>
> #### 一个 html 中 <span style="color:red;font-weight:bold">可以有多个 &lt;script&gt; 标签</span>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>小标题</title>
    <style>
      /* 通过选择器确定样式的作用范围 */
      .btn1 {
        display: block;
        width: 150px;
        height: 40px;
        background-color: rgb(245, 241, 129);
        color: rgb(238, 31, 31);
        border: 3px solid rgb(238, 23, 66);
        font-size: 22px;
        font-family: "隶书";
        line-height: 30px;
        border-radius: 5px;
      }
    </style>
    <script>
      function sayhello() {
        alert("hello , javascript");
      }
    </script>
  </head>

  <body>
    <button class="btn1" onclick="sayhello()">点我有惊喜</button>
  </body>
</html>
```

#### 效果图

![alt text](js引入效果.png)

<hr/>

### 外部式

#### 基本介绍

> #### <span style="color:red;font-weight:bold">src</span> 属性：用于指定脚本文件路径
>
> #### <span style="color:red;font-weight:bold">type</span> 属性：text / javascript

#### 注意点

> #### &lt;script&gt; 标签<span style="color:red;font-weight:bold">必须是一对</span>的方式引入，否则在调用相关函数时无法生效
>
> #### 一对 script 标签<span style="color:red;font-weight:bold">不能再引入外部 js 文件的同时定义内部脚本</span>
>
> #### script 标签如果用于引入外部 js 文件，<span style="color:red;font-weight:bold">中间最好不要有任何字符，包括空格和换行</span>

#### js 脚本文件

```js
function sayhello() {
  alert("hello , javascript");
}
```

#### 引入外部脚本文件

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>小标题</title>
    <style>
      /* 通过选择器确定样式的作用范围 */
      .btn1 {
        display: block;
        width: 150px;
        height: 40px;
        background-color: rgb(245, 241, 129);
        color: rgb(238, 31, 31);
        border: 3px solid rgb(238, 23, 66);
        font-size: 22px;
        font-family: "隶书";
        line-height: 30px;
        border-radius: 5px;
      }
    </style>
    <script src="./button.js" type="text/javascript"></script>
  </head>

  <body>
    <button class="btn1" onclick="sayhello()">点我有惊喜</button>
  </body>
</html>
```

## 变量声明

#### JS 中的变量具有如下特征

> 1.  **js 中的变量类型都是<span style="color:red;font-weight:bold">弱类型变量</span>,可以<span style="color:red;font-weight:bold">统一声明成 var</span>**
> 2.  **var 声明的变量<span style="color:red;font-weight:bold">可以再次声明</span>**
> 3.  **变量可以使用不同的数据类型<span style="color:red;font-weight:bold">多次赋值</span>**
> 4.  **JS 的语句可以以; 结尾,也可以不用;结尾**
> 5.  **变量标识符<span style="color:red;font-weight:bold">严格区分大小写</span>**
> 6.  **标识符的命名规则参照 JAVA**
> 7.  **如果使用了 一个<span style="color:red;font-weight:bold">没有声明的变量</span>,那么运行时会报 uncaught ReferenceError: \*\*\* is not defined at index.html:行号:列号**
> 8.  **如果一个变量<span style="color:red;font-weight:bold">只声明,没赋值</span>,那么值是 <span style="color:red;font-weight:bold">undefined</span>**

## 数据类型

#### 数值类型

> - <h4>数值类型统一为 <span style="color:red;font-weight:bold">number</span>,不区分整数和浮点数</h4>

#### 字符串类型

> - <h4>字符串类型为 <span style="color:red;font-weight:bold">string</span> 和 JAVA 中的 String 相似,JS 中<span style="color:red;font-weight:bold">不严格区分单双引号</span>,都可以用于表示字符串</h4>

#### 布尔类型

> - <h4>布尔类型为 <span style="color:red;font-weight:bold">boolean</span> 和 Java 中的 boolean 相似,但是在 JS 的 if 语句中,非空字符串会被转换为'真',非零数字也会被认为是'真'</h4>

#### 引用数据类型

> - <h4><span style="color:red;font-weight:bold">引用数据类型</span>对象是 <span style="color:red;font-weight:bold">Object</span> 类型, 各种对象和数组在 JS 中都是 Object 类型</h4>

#### function 类型

> - <h4>JS 中的各种函数属于 <span style="color:red;font-weight:bold">function</span> 数据类型</h4>

#### 命名未赋值

> - <h4>js 为弱类型语言,统一使用 var 声明对象和变量,在赋值时才确定真正的数据类型,变量如果<span style="color:red;font-weight:bold">只声明没有赋值</span>的话,数据类型为 <span style="color:red;font-weight:bold">undefined</span></h4>

#### 赋予 NULL 值

> - <h4>在 JS 中,如果给一个变量赋值为 <span style="color:red;font-weight:bold">null</span>,其<span style="color:red;font-weight:bold">数据类型是 Object</span>, 可以通过 <span style="color:red;font-weight:bold">typeof</span> 关键字<span style="color:red;font-weight:bold">判断数据类型</span></h4>

## 运算符

#### 1. 算数运算符 + - \* / %%

> #### <span style="color:red;font-weight:bold">/</span> 如果 <span style="color:red;font-weight:bold">结果是小数，返回小数</span>，不会取整返回整数
>
> #### <span style="color:red;font-weight:bold">/ 在除 0</span> 时,结果是 <span style="color:red;font-weight:bold">Infinity</span> ,而不是报错
>
> #### <span style="color:red;font-weight:bold">% 在模 0</span> 时,结果是 <span style="color:red;font-weight:bold">NaN</span>,意思为 <span style="color:red;font-weight:bold">not a number</span> ,而不是报错

#### 2. 复合算数运算符 ++ -- += -= \*= /= %=

> #### 在/=0 时,结果是 <span style="color:red;font-weight:bold">Infinity</span> ,而不是报错
>
> #### 在%=0 时,结果是 <span style="color:red;font-weight:bold">NaN</span>,意思为 <span style="color:red;font-weight:bold">not a number</span> ,而不是报错

#### 3. 关系运算符 > < >= <= == === !=

> #### <span style="color:red;font-weight:bold">==</span>：如果两端的数据<span style="color:red;font-weight:bold">类型不一致</span>,会尝试将两端的数据<span style="color:red;font-weight:bold">转换成 number</span>,再对比 number 大小
>
> #### （1）'123' 这种字符串可以转换成数字
>
> #### （2）<span style="color:red;font-weight:bold">true 会被转换成 1；false 会被转换成 0</span>
>
> #### <span style="color:red;font-weight:bold">===</span>：如果两端数据<span style="color:red;font-weight:bold">类型不一致</span>,直接返回 <span style="color:red;font-weight:bold">false</span>,数据类型一致在比较是否相同

#### 4. 逻辑运算符 || &&

> #### 几乎和 JAVA 中的一样,需要注意的是,这里直接就是短路的逻辑运算符,<span style="color:red;font-weight:bold">单个的 | 和 & 以及 ^ 是位运算符</span>

#### 5. 条件运算符 条件? 值 1 : 值 2

> #### 几乎和 JAVA 中的一样

#### 6. 位运算符 | & ^ << >> >>>

> #### 和 java 中的类似(了解)

## 分支结构

#### 弹窗输入函数

> #### <span style="color:red;font-weight:bold">prompt</span>（"提示信息"），<span style="color:red;font-weight:bold">返回字符串</span>，用 <span style="color:red;font-weight:bold">Number.parseInt( ) </span>方法转为整数

```js
var input = prompt("输入一个整数");
var num = Number.parseInt(input);
if (num === 10) {
  console.log("true");
} else {
  console.log("false");
}
```

#### （1）if 结构

> #### if ( ) 中的<span style="color:red;font-weight:bold">非空字符串</span>会被认为是 <span style="color:red;font-weight:bold">true</span>
>
> #### if ( ) 中的<span style="color:red;font-weight:bold">非零数字</span>会被认为是 <span style="color:red;font-weight:bold">true</span>
>
> #### if ( ) 中的<span style="color:red;font-weight:bold">非空对象</span>会被认为是 <span style="color:red;font-weight:bold">true</span>

```js
if ("false") {
  // 非空字符串 if判断为true
  console.log(true);
} else {
  console.log(false);
}
if ("") {
  // 长度为0字符串 if判断为false
  console.log(true);
} else {
  console.log(false);
}
if (1) {
  // 非零数字 if判断为true
  console.log(true);
} else {
  console.log(false);
}
if (new Object()) {
  console.log(true);
} else {
  console.log(false);
}
```

#### （2）switch 结构

> #### 和 Java 相同

## 循环结构
