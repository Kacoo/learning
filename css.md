## CSS(Cascading Style Sheets) 层叠样式表
- CSS样式单独作为文件，在HTML中引用CSS文件，方便使用和管理
- 规定了冲突的规则（层叠）

### 1. 元素
1. 替换元素 replaced element  
用来替换元素内容的部分并非有文档内容直接表示  
最典型的例子是img元素，由文档本身之外的一个图像文件来替换
2. 非替换元素 nonreplaced element
大多数HTML元素是非替换元素，其内容由用户代理（通常是一个浏览器）在元素本身生成的框中显示
比如`<span>``<title>`等

### 2. 元素显示角色
1. 块级元素 block element  
块级元素生成一个元素框，默认会填充其父元素的内容区，旁边不能有其他元素
比如`<p>``<div>`

2. 行内元素 inline element  
行内元素在一个文本行内生成元素狂，而不会打断这行文本
比如`<a>``<em>``<strong>`

### 3. CSS如何与HTML文本关联
1. link标记 外部样式表  
`<link  rel="stylesheet" type="text/css" href="外部样式表路径">`  
为了成功地加载外部样式表，link必须放在head元素中，但不能放在其他元素内（如title）

2. style元素 文档样式表/嵌套样式表  
`<style type="text/css"></style>`

3. @import指令 指示Web浏览器加载一个外部样式表  
@import url(xxx.css)

4. 内联样式 inline style  
为单个元素指定一些样式，而不需要嵌套或外部样式表  
在元素标签内部使用，除body外部出现的元素（如head和title），style属性可以与任何其他HTML元素关联

### 4. CSS注释
/\*这是注释的内容啦\*/

### 5. CSS规则
#### 5.1 规则
每个规则分为2个基本部分：选择器（selector）和声明块（declaration block），每个样式表由一系列规则组成。  
选择器：选择使用该样式的文档元素  
声明块：由一个或多个声明组成，每个声明是一个属性-值对（property-value）。

#### 5.2 选择器分组
将多个选择器放在规则左边，并用一个逗号分隔。声明块中的样式将应用到这两个选择器所引用的元素。  
h1, p {  
    display: inline;  
    color: #ffff00;  
    width: 203px;    
}

__通配选择器__  
CSS引入了新的简单选择器，成为通配选择器（universal selector)，显示为一个星号（*）。与任何元素匹配。  
如：要让一个文档中的每个元素都变成红色  
\* {  
	color: red;  
}

__类选择器__  
.className {  
attr: value;  
}

__ID选择器__  
\#idName {  
attr: value;  
}  

__属性选择器__  

__后代选择器__  

__伪类和伪元素__  

### ?. 属性
1. display  
none  
block  
inline  
list-item  
inline-block  
……  

2. rel 关系，relation    
stylesheet 主样式表  
alternate stylesheet 候选样式表

3. type 描述加载的数据类型  
text/css

4. href url地址，可以是绝对地址/相对地址
5. media 应用的表现媒体  
all 用于所有表现媒体  
aural 用于语音合成器、屏幕阅读器和文档的其他声音表现  
braille  用Braille设备表现文档时使用   
print 为视力正常的用户打印文档时使用，另外还会在显示文档的“打印预览”时使用  
screen 在屏幕媒体（如桌面计算机监视器）中表现文档时使用。在这种系统上运行的所有Web浏览器都是屏幕媒体用户代理  

