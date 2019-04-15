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