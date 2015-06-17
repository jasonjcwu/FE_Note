## 文档树

Document Object Model (DOM) 既文档**对象**模型，其用对象的方式表示对应的文档结构及内容。

下面为一个样例 `p` 元素在文档中的对象所包含的所有属性。

```
p#targetaccessKey: ""
align: ""
attributes: NamedNodeMapbaseURI: ""
childElementCount: 0
childNodes: NodeList[1]
children: HTMLCollection[0]
classList: DOMTokenList[0]
className: ""
clientHeight: 0
clientLeft: 0
clientTop: 0
clientWidth: 0
contentEditable: "inherit"
dataset: DOM
StringMapdir: ""
draggable: false
firstChild: text
firstElementChild: null
hidden: false
id: "target"
innerHTML: "Hello, World!"
innerText: "Hello, World!"
isContentEditable: false
lang: ""
lastChild: textlastElementChild: null
localName: "p"
namespaceURI: "http://www.w3.org/1999/xhtml"nextElementSibling: null
nextSibling: null
nodeName: "P"nodeType: 1nodeValue: null
offsetHeight: 0offsetLeft: 0offsetParent: null
offsetTop: 0offsetWidth: 0onabort: null
onautocomplete: null
onautocompleteerror: null
onbeforecopy: null
onbeforecut: null
onbeforepaste: null
onblur: null
oncancel: null
oncanplay: null
oncanplaythrough: null
onchange: null
onclick: null
onclose: null
oncontextmenu: null
oncopy: null
oncuechange: null
oncut: null
ondblclick: null
ondrag: null
ondragend: null
ondragenter: null
ondragleave: null
ondragover: null
ondragstart: null
ondrop: null
ondurationchange: null
onemptied: null
onended: null
onerror: null
onfocus: null
oninput: null
oninvalid: null
onkeydown: null
onkeypress: null
onkeyup: null
onload: null
onloadeddata: null
onloadedmetadata: null
onloadstart: null
onmousedown: null
onmouseenter: null
onmouseleave: null
onmousemove: null
onmouseout: null
onmouseover: null
onmouseup: null
onmousewheel: null
onpaste: null
onpause: null
onplay: null
onplaying: null
onprogress: null
onratechange: null
onreset: null
onresize: null
onscroll: null
onsearch: null
onseeked: null
onseeking: null
onselect: null
onselectstart: null
onshow: null
onstalled: null
onsubmit: null
onsuspend: null
ontimeupdate: null
ontoggle: null
onvolumechange: null
onwaiting: null
onwebkitfullscreenchange: null
onwebkitfullscreenerror: null
onwheel: null
outerHTML: "<p id="target">Hello, World!</p>"outerText: "Hello, World!"ownerDocument: documentparentElement: null
parentNode: null
prefix: null
previousElementSibling: null
previousSibling: null
scrollHeight: 0
scrollLeft: 0
scrollTop: 0
scrollWidth: 0
shadowRoot: null
spellcheck: true
style: CSSStyle
DeclarationtabIndex: -1
tagName: "P"
textContent: "Hello, World!"
title: ""
translate: true
webkitdropzone: ""
__proto__: HTMLParagraphElement
```

通过使用 DOM 提供的 API (Application Program Interface) 可以动态的修改节点（node），也就是对 DOM 树的直接操作。浏览器中通过使用 JavaScript 来实现对于 DOM 树的改动。

**DOM 包含**

- DOM Core
- DOM HTML
- DOM Style
- DOM Event

### HTML 转换 DOM 树

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>My title</title>
  </head>
  <body>
    <a href="">My Link</a>
    <h1>My header</h1>
  </body>
</html>
```

![](../img/D/dom-tree.gif)

### 节点遍历

```Javascript
var node = document.getElementsByTagName('h1')[0];

node.parentNode; // body
node.firstChild; // null

node.lastChild;  // null

node.previousBibling; // <a href="">My Link</a>
node.nextSibling;     // null

```

### 节点类型

**常用节点类型**

- ELEMENT_NODE 可使用 `document.createElement('elementName');`创建
- TEXT_NODE 可使用 `document.createTextNode('Text Value');` 创建

**不常用节点类型**

- COMMENT_NODE
- DOCUMENT_TYPE_NODE

### 元素遍历

元素节点符合 HTML DOM 树规则。

```
<p>Hello, <em>Xinyang</em>! 回到<a href="http://li-xinyang.com">主页</a>。</p>
```

```
p.firstElementChild; // <em>Xinyang</em>
p.lastElementChild;  // <a href="http://li-xinyang.com">主页</a>

em.nextElementSibling; // <a href="http://li-xinyang.com">主页</a>
em.previousElementSibling; // null

```