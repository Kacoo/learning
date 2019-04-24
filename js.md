1. 一个完整的JavaScript实现应当由3个部分组成  
（1） 核心（ECMAScript）  
（2） 文档对象模型（DOM）  
（3） 浏览器对象模型（BOM）  
2. 常见的Web浏览器是ECMAScript实现可能的宿主环境之一。宿主环境不仅提供ECMAScript实现，同时也提供该语言的扩展（如DOM），以便语言与环境之间对接交互。  
其他宿主环境包括Node（一种服务端JacaScript平台）、Adobe Flash。  
3. ECMAScript包括7部分：  
（1） 语法  
（2） 类型  
（3） 语句  
（4） 关键字  
（5） 保留字  
（6） 操作符  
（7） 对象  
4. ES5发布于2009年  
5. __文档对象模型（DOM, Document Object Model）__  
是针对XML但经过扩展用于HTML的应用程序编程接口（API, Application Programming Interface）。  
DOM把整个页面映射为一个多层节点结构，HTML或XML页面中的每个组成部分都是某种类型的节点，这些节点又包含着不同类型的数据。  
通过DOM创建的表示文档的树形图，开发人员获得控制页面内容和结构的主动权。借助DOM提供的API，开发人员可以轻松自如地删除、添加、替换或修改任何节点。  
6. DOM级别  
（1） DOM Level 1，DOM1级由2个模块组成：DOM核心和DOM HTML。  
（2） DOM Level 2，DOM2级在原来基础上引入和新模块，给出了众多新类型和新接口的定义。  
DOM视图（DOM Views）：定义了跟踪不同文档（例如，应用CSS之前和之后的文档）视图的接口  
DOM事件（DOM Events）：定义了事件和事件处理的接口  
DOM样式（DOM Style）：定义了基于CSS为元素应用样式的接口  
DOM遍历和范围（DOM Traversal and Range）：定义了遍历和操作文档树的接口  
（3） DOM Level 3，DOM3级进一步扩展了DOM  
7. __浏览器对象模型（BOM, Broswer Object Model）__  
（1） 从根本上讲，BOM只处理浏览器窗口和框架  
（2） 人们习惯上把所有针对浏览器的JavaScript扩展算作BOM的一部分，包括：  
（3） 弹出新浏览器窗口的功能  
（4） 移动、所方和关闭浏览器窗口的功能  
（5） 提供浏览器详细信息的navigator对象  
（6） 提供浏览器所加载页面的详细信息的location对象  
（7） 提供用户显示器分辨率详细信息的screen对象  
（8） 对cookies的支持  
（9） 像XMLHttpRequest和IE的ActiveXObject这样的自定义对象  
8. MIME类型：编写代码使用的脚本语言的内容类型。  
9. __函数柯里化currying__
10. 
                setTimeout(function () { 
                    // expressions
                }, 0);