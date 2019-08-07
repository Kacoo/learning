## Programming Experience
### config
基础配置，需要写在单独的文件中，方便进行全局配置。  
比如：服务器地址，环境（生产环境/开发环境）

### 关于HTTP请求的Response-Headers
@2019-06-27  
Response中的Headers是一个`function`，因此如果需要获取Response的Headers，__需要调用`headers()`__，获取token等头部信息。

### localStorage  
@2019-06-28  
1. 存入localStorage的数据（不论是Boolean、Number还是String、Object），会__自动以`JSON`格式存储__。  
因此从localStorage获取数据用来比对的时候，特别注意，需要__先判断key是否存在`if(localStorage.key)`（否则会造成页面白屏）__，再__进行`JSON.parse()`__。

### 在HTTP拦截器注入$state服务，跳转页面（登录页面）
@2019-06-28  
如果在函数体注入$state服务会导致循环依赖的问题，因此需要在返回的具体函数内部手动注入`var stateService = $injector.get('$state');`  
详见StackOverflow解析：[Circular dependency found: $http <- $templateFactory <- $view <- $state](https://stackoverflow.com/questions/25495942/circular-dependency-found-http-templatefactory-view-state)

### AngularJS路由的url必须先接一个路径
@2019-07-01  
在写路由的时候`.state("home", {url: "/home",templateUrl: localRouter + "home.html"})`，其中url不能直接拼接参数（/{id}），一定需要先拼接一个目录（/page/{id}），否则会引起奇怪的错误。  
@2019-07-13  
在写路由的时候，url不能出现重复的组合

### 使用npm安装软件报错`Unexpected end of JSON input`
@2019-07-11  
[解决方案参考](https://github.com/npm/npm/issues/19072)  
1. 清除缓存`npm cache clean --force`  
2. 继续运行原命令