构建一个HTML文档需要哪些基本要素

> HTML文档具有特定的结构 ，最起码要有一些关键性的元素。html文档的基本架构组成包括文档和元数据元素

<center>文档和元数据元素</center>

| 元    素 | 说    明                                           | 类    型     |
| -------- | -------------------------------------------------- | ------------ |
| base     | 设置相对URL的基础                                  | 元数据       |
| body     | 表示 HTML文档的内容                                | 无           |
| DOCTYPE  | 表示 HTML文档的开始                                | 无           |
| head     | 包含文档的元数据                                   | 无           |
| html     | 表示文档中 HTML部分的开始                          | 无           |
| link     | 定义与外部资渊（通常是样式表或网站图标）的关系     | 元数据       |
| meta     | 提供关于文档的信息                                 | 元数据       |
| noscript | 包含浏览器禁用脚本或不支持脚本时显示的内容         | 元数据、短语 |
| script   | 定义脚本程序，可以是文档内嵌的也可以是外部文件中的 | 元数据、短语 |
| style    | 定义CSS样式                                        | 元数据       |
| title    | 设置文档标题                                       | 元数据       |



## 1  基本文档结构

以HTML5为例，一个基本的文档框架应该包含以下内容：

```html
<!DOCTYPE HTML>
<html>
	<head>
        <title></title>
    </head>
	<body></body>
</html>
```

基本元素说明：

| 元素    | 说明                                                         |
| ------- | ------------------------------------------------------------ |
| DOCTYPE | 每个HTML文档都必须以DOCTYPE元素开头。用于告知浏览器文档类型是HTML文档。如果省略，大多数浏览器默认将文档解释为HTML内容。 |
| html    | HTML文档根元素，表示HTML部分的开始。内含head元素和body元素各一，h5新增属性manifest。 |
| head    | 提供有关文档内容和标记的说明信息，也用于包含脚本和外部资源的引用，常见子元素有title、style、script、meta等。 |
| body    | 用于包含文档内容，紧跟head元素之后。                         |

上例中的  DOCTYPE元素让浏览器明白其处理的是  HTML文档。紧跟着  DOCTYPE元素的是html元素的开始标签。它告诉浏览器：自此直到html结束标签，所有元素内容都应作为HTML处理。用了DOCTYPE元 素之后又接着使用html元素看起来可能有点奇怪，其实早在 HTML标准小荷才露尖尖角的时候，具有同等地位的还有一些别的标记语言，文档中可能会混合使用多种标记语言。

如今HTML已成为占绝对优势的标记语言  ，即使在文档中省略   DOCTYPE和html元素，绝大多数浏览器仍会假定自己处理的是HTML文档。不过这并不意味着不必再用这两个元素。这是因们有着重要的用途，而且依赖浏览器的默认行为模式就像轻信陌生人一样不靠谱，多数情况下事情很顺利， 可是冷不防就会出大漏子。



## 2  文档说明元素

### 2.1  title元素

​	title元素用于设置文档标题，每个HTML文档都应该有且仅有一个title元素，但是没有的话浏览器通常也不会在意。大多数浏览器把title元素的内容显示在其窗口的标题栏上或用来显示文档的标签页的标签位置上。

​	示例：`<title>标题</title>`

### 2.2  base元素

​	base元素用于设置HTML文档中的相对URL的解释参考基准，以及设置链接的打开方式，还有提交表单时浏览器如何反应的设置。该元素一般位于head元素中，并且要紧跟head元素，有href、target两个局部属性。href属性设置url基准，target属性设置URL打开方式。
​	示例：`<base href="http://chzroot/" target="_blank"/>`
​	补充：在没设置base元素的情况下，浏览器以当前html文档所在目录为相对链接参考点

### 2.3  meta元素

> 使用meta元素说明文档，它有多种不同用法，并且一个文档中可以包含任意多个或多种meta元素，但每个meta元素只能用于一种用途。

meta元素有name、content、charset和http-equiv四个局部属性，根据功能选择不同的搭配

2.3.1、指定名/值元数据对，用到name和content属性
​	  示例：`<meta name="author" content="chz" />`                    

<center><strong>可用元数据名称</strong></center>

| 元数据名称       | 说明                                                         |
| ---------------- | ------------------------------------------------------------ |
| application name | 当前页所属Web应用系统的名称                                  |
| author           | 当前页作者名                                                 |
| description      | 当前页说明                                                   |
| generator        | 生成HTML页面的软件名称                                       |
| keywords         | 一批以逗号分隔的字符串，页面关键字                           |
| robots           | 搜索引擎处理方式（noindex 不要索引本页、noarchive 不要缓存或存档本页、nofollow 不要接着搜索本页链接） |

2.3.2、声明字符编码，使用charset属性
​	  示例：`<meta charset="utf-8" />`
2.3.3、模拟HTTP标头字段，使用http-equiv和content属性，也是键值对模式指定
​	  示例1：refresh    以秒为单位指定时间间隔，重新载入当前页面或载入指定的URL
​	  如：`<meta http-equiv="refresh" content="5; http:www.baidu.com"/>`  不指定URL默认刷新当前页面
​	  示例2：default-style    指定页面优先使用的样式表，对应content属性与同一文档中某个style元素或link元素的title属性值相同
​	  示例3：content-type    声明文档类型和字符编码，如：`<meta http-equiv="content-type" content="text/html charset=UTF-8"/>  `



## 3  定义CSS样式

使用style元素定义内嵌CSS样式，使用link元素导入外部样式表。
  3.1、style元素
    style元素可以出现在HTML文档中任意可包含子元素的元素中，一个文档可包含多个style元素
    使用type指定样式类型，类型总是为type="text/css"，使用media属性指定样式适用媒体，如：`<style media="screen" type="text/css">`

<center><strong>media属性的设备值</strong></center>

| 值         | 说明                     |
| ---------- | ------------------------ |
| all        | 所有设备                 |
| aural      | 语音合成器               |
| braille    | 盲文设备                 |
| handheld   | 手持设备                 |
| projection | 投影机                   |
| print      | 打印预览和打印页面       |
| screen     | 计算机显示器屏幕         |
| tty        | 电传打字机之类的等宽设备 |
| tv         | 电视机                   |

<center><strong>media属性可使用的特性</strong></center>

| 特性                              | 说明                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| width  height                     | 指定浏览器窗口的宽度和高度。单位为px                         |
| device-width device-height        | 指定整个设备（而不仅仅是浏览器窗口）的宽度和高度。单位为px   |
| resolution                        | 指定设备的像素密度。单位为dpi( 点瑛 寸 ）或dpcm( 点／厘米）  |
| orientation                       | 指定设备的较长边朝向。支持的值有   portrait 和landsc ape。该特性没有限定词 |
| aspect-ratio  device-aspect-ratio | 指定浏览器窗口或整个设备的像素宽高比。其值表示为像素宽度与像素高度的比值 |
| color  monochrome                 | 指定彩色或黑白设备上每个像素占用的二进制位数                 |
| color-index                       | 指定设备所能显示的颜色数目                                   |
| scan                              | 指定电视的扫描模式。支持的值有progressi ve和int erlace 。该特性没有限定词 |
| grid                              | 指定设备的类型。网格型设备使用固定的网格显示内容，例如基于字符的终端和单行显示的寻呼机。支持的值有 0和I  ( I代表网格型设备）。该特性没有限定词 |

使用连接词来组合设备和特性条件。连接词有：AND、NOT和表示OR的逗号(,)。特性通常跟限定词min和max配合使用，也可以使用精准的尺寸。
	示例：`<style media="screen AND (min-width:500px)" type="text/css"/>`

HTML5新增了scoped属性，用于指定样式作用范围：如果style元素中有 scoped属性存在，那么其中定义的样式只作用于该元素的父元素及兄弟元素。要是不用scoped属性的话，在HTML文档中任何地方用style元素定义的样式都将作用于整个文档。

补充：vue组件中使用scoped属性表示样式只应用于当前组件

  3.2、link元素
	指定外部资源,一个文档可以使用多个link标签指定外部资源：

<center><strong>link元素说明</strong></center>

| 项目      | 说明                                              |
| --------- | ------------------------------------------------- |
| 父元素    | head、noscript                                    |
| 局部属性  | href、rel、hreflang、media、type、sizes           |
| HTML5变化 | 新增sizes属性。原来的charset、rev和target属性废除 |



<center><strong>link局部属性</strong></center>

| 属性     | 说明                                                 |
| -------- | ---------------------------------------------------- |
| href     | 指定资源URL                                          |
| hreflang | 说明关联资源使用的语言                               |
| media    | 参考style元素media用法                               |
| rel      | 说明文档与所关联资源的关系类型                       |
| sizes    | 指定图标的大小。                                     |
| type     | 指定所关联资源的MIME类型， 如text/css、 image/x-icon |



<center><strong>rel属性取值</strong></center>

| 值         | 说明                                                         | 示例                                                         |
| ---------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| alternate  | 链接到文档的替代版本，比如另一种语言的译本                   |                                                              |
| author     | 链接到文档的作者                                             |                                                              |
| help       | 链接到当前文档的说明文档                                     |                                                              |
| icon       | 指定图标资源，如果网站标识文件位于/favicon.ico，即网页根目录下，即使不使用link元素，浏览器也会自动请求该文件，从而显示网站标识。 | `<link rel="shortcut icon" href="favicon.ico" type="image/x-icon"/>` |
| license    | 链接到当前文档的相关许可证                                   |                                                              |
| pingback   | 指定一个回探  ( pingback )  服务器。从其他网站链接到博客的时候它能自动得到通知 |                                                              |
| pre-fetch  | 预先获取一个资源（支持性不好）                               | `<link rel="prefetch" href="/page2.html"/>`                  |
| stylesheet | 载人外部样式表                                               | `<link rel="stylesheet" type="text/css" href="test.css"/>`   |



## 4  使用脚本元素

### 4.1  script元素

scrtip元素用于在页面中加入脚本，常用脚本类型是javascript。script元素有两种形式：内嵌脚本和外部脚本。

<center><strong>script元素说明</strong></center>

| 项目      | 说明                                                         |
| --------- | ------------------------------------------------------------ |
| 父元素    | 可以包含子元素的任何元素                                     |
| 局部属性  | type、src、defer、async、charset                             |
| HTML5变化 | 默认类型为javascript，type属性可有可无，新增async属性，废除language属性 |



<center><strong>script元素的局部属性</strong></center>

| 属性         | 说明                                                         |
| ------------ | ------------------------------------------------------------ |
| type         | 表示所引用或定义的脚本的类型，对于JavaScript脚本这个属性可以省略 |
| src          | 指定外部脚本文件的URL                                        |
| defer、async | 设定外部脚本的执行方式。这两个属性只能与src属性一同使用      |
| charset      | 说明外部脚本文件所用字符编码，该属性只能与src属性一同使用    |

内嵌脚本示例：`<script>alert("Hello javascript");</script>`
载入外部脚本示例：`<script src="text.js"></script>`
defer属性用于加载外部脚本文件，作用是推迟脚本执行，相当于将该script标签置于文档最后：`<script defer src="text.js"></script>`
async属性作用是异步执行脚本，一般用于不需要与HTML文档元素相互作用的脚本：`<script async src="text.js"></script>`

使用了async属性后 ，浏览器将在继续解析HTML文档中其他元素（包括其他script 元素 ）的同时异步加载和执行脚本。如果运用得当，这可以大大提高整体加载性能。

### 4.2  noscript元素

​	noscript元素用于向禁用了Javascript或浏览器不支持Javascript的用户显示一些内容。

示例：
	提示要求Javascript:`<noscript>Javscript is required!</noscript>`
	也可以在浏览器不支持Javascript时将其引至另一个URL：`<noscript><meta http-equiv="refresh" content="0; http://www.baidu.com"/></noscript>`



## 5  文档内容

文档内容应该放在body元素内，如`<body>我是文档内容</body>`，body元素的一些属性（alink、background、bgcolor、link、margintop、marginbottom 、marginleft 、marginright、margiwidth、text和vlink）在HTML5中已不再使用。这些属性的效果可用CSS实现。

body元素的浏览器习惯样式示例：

```css
body{display:block;margin:8px;}
body:focus{outline:none;}
```

