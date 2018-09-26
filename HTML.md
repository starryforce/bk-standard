# 整体结构
## HTML基础设施
* 文件应以 `<!DOCTYPE ......>` 首行顶格开始，推荐使用 `<!DOCTYPE html>`。
* 必须申明文档的编码 charset，且与文件本身编码保持一致，推荐使用 UTF-8 编码 <meta charset="utf-8"/>。
* 根据页面内容和需求填写适当的 keywords 和 description。
* 页面 title 是极为重要的不可缺少的一项。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"/>
<title>bebefocus</title>
<meta name="keywords" content=""/>
<meta name="description" content=""/>
<meta name="viewport" content="width=device-width"/>
<link rel="stylesheet" href="css/style.css"/>
<link rel="shortcut icon" href="img/favicon.ico"/>
<link rel="apple-touch-icon" href="img/touchicon.png"/>
</head>
<body>
</body>
</html>
```

## 结构顺序和视觉顺序基本保持一致
* 按照从上至下、从左到右的视觉顺序书写 HTML 结构。
* 有时候为了便于搜索引擎抓取，我们也会将重要内容在 HTML 结构顺序上提前。
* table 不建议用于布局，但表现具有明显表格形式的数据，table 还是首选。

## 结构、表现、行为三者分离，避免内联
* 使用 link 将 css 文件引入，并置于 head 中。
* 使用 script 将 js 文件引入，并置于 body 底部。

## 保持良好的简洁的树形结构
* 每一个块级元素都另起一行，每一行都使用 Tab 缩进对齐（head 和 body 的子元素不需要缩进）。
* 删除冗余的行尾的空格。
* 使用4个空格代替1个 Tab（编辑器可设置）。
* 对于内容较为简单的表格，建议将 tr 写成单行。
* 大的模块之间用空行隔开，使模块更清晰。

```html
<body>
<!-- 侧栏内容区 -->
<div class="m-side">
    <div class="side">
        <div class="sidein">
            <!-- 热门标签 -->
            <div class="sideblk">
                <div class="m-hd3"><h3 class="tit">热门标签</h3> </div>
                ...
            </div>
            <!-- 最热TOP5 -->
            <div class="sideblk">
                <div class="m-hd3"><h3 class="tit">最热TOP5</h3> <a href="#" class="s-fc02 f-fr">更多»</a></div>
                ...
            </div>
        </div>
    </div>
</div>
<!-- /侧栏内容区 -->
</body>
```

## 另外，请做到以下几点
* 结构上如果可以并列书写，就不要嵌套。
  如果可以写成 `<div></div><div></div>` 那么就不要写成 `<div><div></div></div>`

* 如果结构已经可以满足视觉和语义的要求，那么就不要有额外的冗余的结构。
  比如 `<div><h2></h2></div>` 已经能满足要求，那么就不要再写成 `<div><div><h2></h2></div></div>`

* 一个标签上引用的 className 不要过多，越少越好。
  比如不要出现这种情况：`<div class="class1 class2 class3 class4"></div>`

* 对于一个语义化的内部标签，应尽量避免使用 className。
  比如在这样一个列表中，li 标签中的 itm 应去除：`<ul class="m-help"><li class="itm"></li><li class="itm"></li></ul>`

# 代码格式
## 说明文案的注释方法
采用类似标签闭合的写法，与 HTML 统一格式；注释文案两头空格，与 CSS 注释统一格式。

* 开始注释：<!-- 注释文案 -->（文案两头空格）。
* 结束注释：<!-- /注释文案 -->（文案前加“/”符号，类似标签的闭合）。
* 允许只有开始注释！

```html
<!-- 头部 -->
<div class="g-hd">
    <!-- LOGO -->
    <h1 class="m-logo"><a href="#">LOGO</a></h1>
    <!-- /LOGO -->
    <!-- 导航 -->
    <ul class="m-nav">
        <li><a href="#">NAV1</a></li>
        <li><a href="#">NAV2</a></li>
        <!-- 更多导航项 -->
    </ul>
    <!-- /导航 -->
</div>
<!-- /头部 -->
```

## 代码本身的注释方法
单行代码的注释也保持同行，两端空格；多行代码的注释起始和结尾都另起一行并左缩进对齐。

```html
<!-- <h1 class="m-logo"><a href="#">LOGO</a></h1> -->
<!--
<ul class="m-nav">
    <li><a href="#">NAV1</a></li>
    <li><a href="#">NAV2</a></li>
</ul>
-->
```

##严格的嵌套
* 尽可能以最严格的 xhtml strict 标准来嵌套，比如内联元素不能包含块级元素等等。
* 正确闭合标签且必须闭合。

## 严格的属性
* 属性和值全部小写，每个属性都必须有一个值，每个值必须加双引号。
* 没有值的属性必须使用自己的名称做为值（checked、disabled、readonly、selected等等）。
* 可以省略 style 标签和 script 标签的 type 属性。

# 内容语义
## 内容类型决定使用的语义标签
在网页中某种类型的内容必定需要某种特定的 HTML 标签来承载，也就是我们常常提到的根据你的内容语义化 HTML 结构。

## 加强“资源型”内容的可访问性和可用性
在资源型的内容上加入描述文案，比如给 img 添加 alt 属性，在 audio 内加入文案和链接等等。

## 加强“不可见”内容的可访问性
背景图上的文字应该同时写在 html 中，并使用 css 使其不可见，有利于搜索引擎抓取你的内容，也可以在 css 失效的情况下看到内容。

## 适当使用实体
以实体代替与 HTML 语法相同的字符，避免浏览解析错误。

<table>
    <caption>常用HTML字符实体（建议使用实体）：</caption>
    <thead>
        <tr><th>字符</th><th>名称</th><th>实体名</th><th>实体数</th></tr>
    </thead>
    <tbody>
        <tr><td>"</td><td>双引号</td><td>&amp;quot;</td><td>&amp;#34;</td></tr>
        <tr><td>&amp;</td><td>&amp;符</td><td>&amp;amp;</td><td>&amp;#38;</td></tr>
        <tr><td>&lt;</td><td>左尖括号（小于号）</td><td>&amp;lt;</td><td>&amp;#60;</td></tr>
        <tr><td>&gt;</td><td>右尖括号（大于号）</td><td>&amp;gt;</td><td>&amp;#62;</td></tr>
        <tr><td>&nbsp;</td><td>空格</td><td>&amp;nbsp;</td><td>&amp;#160;</td></tr>
        <tr><td>　</td><td>中文全角空格</td><td>&nbsp;</td><td>&amp;#12288;</td></tr>
    </tbody>
</table>
   
   
<table>
    <caption>常用特殊字符实体（不建议使用实体）：</caption>
    <thead>
        <tr><th>字符</th><th>名称</th><th>实体名</th><th>实体数</th></tr>
    </thead>
    <tbody>
        <tr><td>¥</td><td>元</td><td>&amp;yen;</td><td>&amp;#165;</td></tr>
        <tr><td>¦</td><td>断竖线</td><td>&amp;brvbar;</td><td>&amp;#166;</td></tr>
        <tr><td>©</td><td>版权</td><td>&amp;copy;</td><td>&amp;#169;</td></tr>
        <tr><td>®</td><td>注册商标R</td><td>&amp;reg;</td><td>&amp;#174;</td></tr>
        <tr><td>™</td><td>商标TM</td><td>&amp;trade;</td><td>&amp;#8482;</td></tr>
        <tr><td>·</td><td>间隔符</td><td>&amp;middot;</td><td>&amp;#183;</td></tr>
        <tr><td>«</td><td>左双尖括号</td><td>&amp;laquo;</td><td>&amp;#171;</td></tr>
        <tr><td>»</td><td>右双尖括号</td><td>&amp;raquo;</td><td>&amp;#187;</td></tr>
        <tr><td>°</td><td>度</td><td>&amp;deg;</td><td>&amp;#176;</td></tr>
        <tr><td>×</td><td>乘</td><td>&amp;times;</td><td>&amp;#215;</td></tr>
        <tr><td>÷</td><td>除</td><td>&amp;divide;</td><td>&amp;#247;</td></tr>
        <tr><td>‰</td><td>千分比</td><td>&amp;permil;</td><td>&amp;#8240;</td></tr>
    </tbody>
</table>