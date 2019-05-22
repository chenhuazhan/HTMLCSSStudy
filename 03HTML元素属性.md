## HTML元素属性(attribute)

> HTML 标签可以拥有属性,属性提供了有关 HTML 元素的更多的信息。



属性只能用在开始标签或单个标签上，不能用于结束标签。一般属性具有名称和值两部分，比如：<input type="text"/>。布尔属性可以不设置值，如：<div contenteditable></div>。



元素属性分类：全局属性（可用于所有HTML元素）、局部属性（仅限于部分元素使用）



属性值定界符：单/双引号皆可，推荐双引号，在某些个别的情况下，比如属性值本身就含有双引号，那么必须使用单引号，有些情况下不写定界符也没事



一个元素多个属性：

​	属性分隔符：一个或多个空格/换行

​	属性顺序：无序



自定义属性：data-属性名



属性和属性值对大小写不敏感。推荐小写的属性/属性值







## HTML 全局属性

> 全局属性 ( global attribute )用来配置所有元素共有的行为。它们可以用在任何一个元素身上，不过这不一定会带来有意义或有用的行为改变。下面将会介绍所有全局属性并示范其用法。





| 属性                                                         | 描述                                                         | eg                                                           |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [accesskey](http://www.w3school.com.cn/tags/att_standard_accesskey.asp) | 规定激活元素的快捷键。目的是让网页或网站的熟客可以使用快捷键访问经常用到的元素。用来触发access key机制的按键组合因平台而异  ，在windows系统上是同时按下 Alt键和 accesskey 属性值对应的键。 | `<input type="password" name="passwd" accesskey="p"/>`触发快捷键后该input元素获得焦点。 |
| [class](http://www.w3school.com.cn/tags/att_standard_class.asp) | 规定元素的一个或多个类名（引用样式表中的类），多个类之间用一个或多个空格/换行符分隔。 | `<div class="class1 class2"></div>`                          |
| [contenteditable](http://www.w3school.com.cn/tags/att_global_contenteditable.asp)     5 | 规定元素内容是否可编辑。该属性值设置为true时用户可以编辑元素内容，用户单击元素后即可开始编辑其内容。设置为 false时则禁止编辑。如果未设定其值，那么元素会从父元素处继承该属性的值。 | `<p contenteditable="true"></p>`                             |
| [contextmenu](http://www.w3school.com.cn/tags/att_global_contextmenu.asp)5 | 规定元素的上下文菜单。上下文菜单在用户点击元素时显示（Windows用户鼠标右击）。支持性还不行，要使用 js 事件来实现该功能。 |                                                              |
| [data-*](http://www.w3school.com.cn/tags/att_global_data.asp)5 | 用于存储页面或应用程序的私有定制数据。                       | `<p data-index="1"><p data-index="2">`                       |
| [dir](http://www.w3school.com.cn/tags/att_standard_dir.asp)  | 规定元素中内容的文本方向。                                   | `<p dir="rtl"></p><p dir="ltr"></p>`                         |
| [draggable](http://www.w3school.com.cn/tags/att_global_draggable.asp)5 | 规定元素是否可拖动。                                         |                                                              |
| [dropzone](http://www.w3school.com.cn/tags/att_global_dropzone.asp)5 | 规定在拖动被拖动数据时是否进行复制、移动或链接。与draggable搭配使用 |                                                              |
| [hidden](http://www.w3school.com.cn/tags/att_global_hidden.asp)5 | 规定元素仍未或不再相关。布尔属性，浏览器隐藏显示。           | `<p hidden>看不到隐藏内容</p>`                               |
| [id](http://www.w3school.com.cn/tags/att_standard_id.asp)    | 规定元素的唯一 id。                                          | `<p id="id1"></p>`                                           |
| [lang](http://www.w3school.com.cn/tags/att_standard_lang.asp) | 规定元素内容的语言。l an讽 性值必须使用有效的ISO语言代码。关于如何声明语言的全面说明可参阅这个网址:http://tools.ietf.org/html/bcp47。不过要注意，语言是个复杂的技术性问题。使用lang属性的目的是让浏览器调整其表达元素内容的方式。比如说，改变使用的引号使用了文字朗读器（或别的残障辅助技术）的情况下正确发音。lang属性还可以用来选择指定语言的内容，以便只显示用户所选语言的内容或对其应用样式。 | `<html lang="en"></html>`                                    |
| [spellcheck](http://www.w3school.com.cn/tags/att_global_spellcheck.asp)5 | 规定是否对元素进行拼写和语法检查。这个属性只有用在用户可以编辑的元素（如input、textarea）上时才有意义。 | `<textarea spellcheck="true"></textarea>`                    |
| [style](http://www.w3school.com.cn/tags/att_standard_style.asp) | 规定元素的行内 CSS 样式。                                    | `<p style="color:red; font-size:20px"></p>`                  |
| [tabindex](http://www.w3school.com.cn/tags/att_standard_tabindex.asp) | 规定元素的 tab 键次序。tabindex值为 1的元素会第一个被选中。用户按一下    Tab键后 ，t abinde x值为 2的那个元素会被选中，依次类推。 tabindex设置为- 1的元素不会在用户按下Tab的键后被选中。 | ` <input  type="text"  name="name"  tabi ndex="1">
<input  type="text" name="city" tabindex="-1">
 <input  type="text"  name="country"  tabi ndex="2">` |
| [title](http://www.w3school.com.cn/tags/att_standard_title.asp) | 规定有关元素的额外信息。浏览器通常用这些东西显示工具提示。   | `<a href="http://www.baidu.com" title="百度一下">百度<a>`    |
| [translate](http://www.w3school.com.cn/tags/att_global_translate.asp)5 | 规定是否应该翻译元素内容。                                   |                                                              |

