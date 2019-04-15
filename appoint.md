# 学习预约系统代码
## 管理后台
### 1. __文件分布__  
#### (1) common文件夹  
存放公用的内容，比如公用的css/图片/需要下载的内容等。
#### (2) module文件夹  
存放各个模块的业务代码，个性化js/css/html。
#### (3) app.js  
AngularJS的主js文件。  
1. 规定了Angular应用的模块及其依赖模块。  
2. 定义了Angular的路由。  
使用`$stateProvider.state.call()`方法代替直接的`$stateProvider.state()`方法（好处是？）。  
3. 定义缺省路由：`$urlRouterProvider.otherwise(path);`  
4. 定义各种常量  
5. `element.addEventListener()`添加事件  
6. 将常用的查询条件封装成一个组件，方便调用。  
7. 函数柯里化Currying  
__猜想1：__针对多个参数的函数，变成只传入一个参数的函数，针对其他的参数，传的那个变化很大的参数保留不变（继续传），其他参数通过定义不同的方法来实现。  
比如原本调用f(a, b)，是两个参数，后面简化成f.f1(a)，f.f2(a)……，参数a是那种无法确定参数值范围的。然后对f()方法的实现中根据参数b可能的取值写n种实现，就是后面的f1-fn  
__维基定义：__在计算机科学中，柯里化（英语：Currying），又译为卡瑞化或加里化，是把接受多个参数的函数变换成接受一个单一参数（最初函数的第一个参数）的函数，并且返回接受余下的参数而且返回结果的新函数的技术。  
8. 菜单栏Controller：定义该系统个性化的菜单方法（大多数是默认查询条件，菜单栏的隐藏和显示），与框架的基础Controller内容合并。  
__问题：__该方法依赖console模块下的`$menuController`，`$menuController`如何处理默认查询条件，使其在页面正常运作？

#### (4) boot.js  
将系统依赖的js和css文件，通过boot.js加载，而不是直接写在html中，提高html文件的可阅读性。（与AngularJS无关）  
包含3个方法：生成加载js文件的语句数组、生成加载css文件的语句数组、将加载js和css文件的语句通过dom操作方法添加到html页面上。  
该js是包裹在一对小括号()中的，表示立即执行内容。  
#### (5) forgetpwd.html  
#### (6) index.html  
主要的html框架文件。  
`<meta charset="UTF-8">`文档字符集，使用UTF-8编码。  
`<base href="/">`  
`boot.js`进入页面需要加载的js文件  
`<body ng-app="project.console"></body>`定义AngularJS应用名  
`<ui-view></ui-view>`在`<body>`标签内定义，表示其余模板html是在`<ui-view>`标签内展示的  
#### (7) login.html
后台登录页面html，用户未登录/登录过期时会强制重定向到该页面。  
当浏览器访问系统时，服务器会根据用户是否已经登录，来判断用户该访问哪个页面。
#### (8) menu.json  
定义了后台菜单的列表，包括菜单名称、菜单ID、对应权限ID、扩展参数（一般是预置查询条件）