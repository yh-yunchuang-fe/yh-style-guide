## 前端编码规范
> 不管有多少人共同参与同一项目，一定要确保每一行代码都像是同一个人编写的。

### 目录
[命名规则](#命名规则)
* [项目命名](#项目命名)
* [目录命名](#目录命名)

[HTML](#HTML)
* [语法](#语法)
* [HTML5 doctype](#HTML5-doctype)
* [lang 属性](#lang 属性)
* [字符编码](#字符编码)
* [IE 兼容模式](#IE 兼容模式)
* [引入 CSS、JS](#引入 CSS、JS)
* [boolean 属性](#boolean 属性)
* [减少标签数量](#减少标签数量)
* [实用高于完美](#实用高于完美)

[CSS](#CSS)
* [语法](#语法)
* [Class命名](#Class命名)
* [声明顺序](#声明顺序)

[JavaScript](#JavaScript)


### 命名规则
#### 项目命名
项目名全部采用小写方式， 以中划线分隔。 比如： my-project-name

#### 目录命名
由于我们使用React技术栈，  
放组件目录名：components  
放页面目录名：containers/pages  
Redux目录名：reducers  
单个组件或页面名每个单词的首字母需大写，如：SearchList


### HTML
#### 语法
* 使用 `4` 个空格做为一个缩进层级，不允许使用 `2` 个空格或 `tab` 字符

* 在属性上，使用双引号 `""`，不要使用单引号 `''`

* 属性名 / 属性值全小写，用中划线 `-` 做分隔符

* 不要在自动闭合标签结尾处使用斜线，例：`<img>`

* 不要忽略可选的关闭标签，例：`</li>` 和 `</body>`

* 自定义属性必须使用 `data-` 前缀

```html
<!-- good -->
<body>
    <img src="logo.png" alt="logo">
    <ul>
        <li class="first-child">first</li>
        <li data-index="2">second</li>
    </ul>
</body>
```

#### HTML5 doctype
<h3 id="HTML5-doctype">HTML5 doctype</h3>

在页面开头使用这个简单的 doctype 来启用标准模式，使其在每个浏览器中尽可能一致的展现

虽然 doctype 不区分大小写，但是按照惯例，doctype 使用全大写

```html
<!-- good -->
<!DOCTYPE html>
```

#### lang 属性

根据HTML5规范：

> 应在 html 标签上加上 lang 属性。这会给语音工具和翻译工具帮助，告诉它们应当怎么去发音和翻译。

在 sitepoint 上可以查到 [语言列表](https://www.sitepoint.com/web-foundations/iso-2-letter-language-codes/)

但 sitepoint 只是给出了语言的大类，例如中文只给出了 zh，但是没有区分香港，台湾，大陆。而微软给出了一份更加详细的 [语言列表](https://msdn.microsoft.com/en-us/library/ms533052(v=vs.85).aspx)，其中细分了 zh-cn, zh-hk, zh-tw

```html
<!DOCTYPE html>
<html lang="zh-cn">
</html>
```

#### 字符编码

通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为 "utf-8"

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
    </head>
</html>
```

#### IE 兼容模式

用 `<meta>` 标签可以指定页面应该用什么版本的 IE 来渲染，PC 端项目，建议启用 IE Edge 模式

```html
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    </head>
</html>
```

#### 引入 CSS、JS

* 根据 HTML5 规范, 通常在引入 CSS 和 JS 时不需要指明 `type`，因为 `text/css` 和 `text/javascript` 分别是他们的默认值

* 在引入 CSS 时，必须指明 `rel="stylesheet"`

* 将 script 放在页面中间将阻断页面的渲染，出于性能方面的考虑，如非必要，JavaScript 应当放在页面末尾

```html
<html>
    <head>
        <link rel="stylesheet" src="index.css">
    </head>
    <body>
        <script src="index.js"></script>
    </body>
</html>
```

#### boolean 属性

boolean 属性指不需要声明取值的属性，XHTML 需要每个属性声明取值，但是 HTML5 并不需要

```html
<!-- good -->
<input type="text" disabled>
<input type="checkbox" value="1" checked>

<!-- bad -->
<input type="text" disabled="disabled">
<input type="checkbox" value="1" checked="true">
```

#### 减少标签数量

在编写HTML代码时，需要尽量避免多余的父节点

```html
<!-- good -->
<img class="logo" src="logo.png">

<!-- bad -->
<span class="logo">
    <img src="logo.png">
</span>
```

#### 实用高于完美

* 尽量遵循 HTML 标准和语义，但是不应该以浪费实用性作为代价

* 任何时候都要用尽量小的复杂度和尽量少的标签来解决问题


### CSS
#### 语法
* 使用 4 个空格作为一个缩进层级，不允许使用 2 个空格或 tab 字符。
* 为了代码的易读性，在每个声明的左括号前增加一个空格。
* { 后需要换行，} 前需要换行
* 每条声明 : 后应该插入一个空格。
* 每条声明应该只占用一行来保证错误报告更加准确。
* 每个属性声明末尾都要加分号
* 引号统一使用双引号
* 属性选择器中的属性值需要引号
* 所有的十六进制值都应该使用小写字母，例如 #fff。
* 尽可能使用短的十六进制数值，例如使用 #fff 替代 #ffffff。
* 不要为 0 指明单位，比如使用 margin: 0; 而不是 margin: 0px;
* 带有取值前面不必要的 0 (比如，使用 .5 替代 0.5)

#### Class命名
* 保持 Class 命名为全小写，可以使用短划线（不要使用下划线和 camelCase 命名）。短划线应该作为相关类的自然间断。(例如，.btn 和 .btn-danger)。
* Class 的命名应该尽量短，也要尽量明确。
* 使用有意义的名称；使用结构化或者作用目标相关，而不是抽象的名称。

#### 声明顺序
相关的属性声明应该以下面的顺序分组处理：  
1.影响文档流的属性（比如：display / position / float / clear / visibility 等）  
2.自身盒模型的属性（比如：width / height / margin / padding / border 等）  
3.排版相关属性（比如：font / line-height / text-align / vertical-align 等）  
4.装饰性属性（比如：color / background / opacity / cursor 等）   
5.CSS3 新特性（比如：transform / transition / animation 等）  
Positioning 处在第一位，因为他可以使一个元素脱离正常文本流，并且覆盖盒模型相关的样式。盒模型紧跟其后，因为他决定了一个组件的大小和位置。  
其他属性只在组件 内部 起作用或者不会对前面两种情况的结果产生影响，所以他们排在后面。


### JavaScript
#### 缩进
* 使用 `4` 个空格做为一个缩进层级，不允许使用 `2` 个空格 或 `tab` 字符  
* `switch` 下的 `case` 和 `default` 必须增加一个缩进层级  
```javascript
switch (variable) {
    case 1:
        break;
    default:
        break;
}
```

#### 空格
* 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格
* 用作代码块起始的左花括号 `{` 前必须有一个空格
* `if / else / for / while / function / switch / do / try / catch / finally` 等关键字后，必须有一个空格
* 在非三目运算符中，`:` 之后必须有空格，之前不允许有空格
* `,` 和 `;` 之前不允许有空格，之后必须有空格
* 函数名和 `(` 之间不允许有空格
* 单行注释 `//` 后需要空格（若单行注释和代码同行，则 `//` 前也需要）
* 行尾不得有多余的空格

```javascript
let len = !arr.length;
if (len) {
    Demo(1, 2);
}

// 函数
function Demo(a, b) {
    let obj = { // 对象
        a: 1
    }
}
```

#### 空行

* 代码块注释前与代码块后保留一个空行

```javascript
let a = 1;
// 注释
if (a == 2) {
    return;
}

a = 2;
```

#### 换行

* 每个语句必须另起一行

* 变量赋值后需要换行

* 左大括号 `{` 后需要换行，右大括号 `}` 前需要换行

```javascript
let a, b,
    c = true;
if (c) {
    return;
}
```

#### 注释

* 单行注释使用 `//`，多行注释使用 `/* */`

* 缩进与下一行代码保持一致

* 文档 / 接口注释使用以下写法

```javascript
/**
 * 文档描述
 * @author 作者
 * @date 创建时间
 * @update 更新者 更新时间
 */

/**
 * 接口描述
 * @param {String} title - 弹窗标题内容
 * @param {String} cancelBtnText = '默认值' - 取消按钮文本
 * @param {object} obj - 参数 obj 为一个对象
 * @param {String} obj.str - 参数 obj 的 str 属性
 */
function (title, cancelBtnText, obj) {
}
 ```

#### 引号

最外层统一使用单引号 `''`

```javascript
let str = '<div id="test"></div>';
```

#### 命名

* 标准变量使用驼峰命名

```javascript
let strObj = '{a: 1}';
```

* 常量全大写，用下划线连接

```javascript
const MAX_COUNT = 10;
```

* 类 / 构造函数每个单词首字母大写

```javascript
function TextNode(options) {
}
```

* jquery 对象必须以 `$` 开头命名

```javascript
let $body = $('body');
```

## 变量声明

* 变量在使用前必须通过 `var / let / const` 定义

* 不要使用未声明的变量，也不要先使用后声明

```javascript
let name = 'MyName';
```

#### 对象

对象属性名不需要加引号，有特殊字符除外

```javascript
let obj = {
    name: 'test',
    age: 20,
    'max-weight': 60
};
```

#### 大括号

`if / else / for / while / do / switch / try / catch` 等关键字后必须有大括号（即使代码块的内容只有一行）

```javascript
if (true) {
    return;
}
```

#### 其他

* 用 `===`, `!==` 代替 `==`, `!=`

* debugger 不要出现在生产环境的代码里

* 不要在循环内部声明函数

* 不允许有空的代码块
