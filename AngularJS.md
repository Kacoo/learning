## 定义服务
provider  
factory  
service  

## 过滤器 filter
格式化数据  
Angular内置了很多过滤器：currency/date/number/uppercase  
自定义过滤器 .filter

## $valid
可以通过这个属性获取表单`<form>`的校验状态

## 当controller变化的时候，做的操作
	$scope.$on('$destroy', function() {
		$interval.cancel(getQuotaInterval);
	})

## emit()
可以向上级controller发送一些信息，用来通信

## HttpInterceptor Http拦截器
AngularJs的HttpInterceptor内置了4个方法，用来对request/requestError/response/responseError做统一的操作。
### 自定义拦截器之后，需要确保所创建的拦截器是拦截器链的一部分
【写法一】  

    .config(["$httpProvider", function ($httpProvider) {
        $httpProvider.interceptors.push("HttpInterceptor");
    }])

【写法二】  

	$httpProvider.responseInterceptor.push('myInterceptor');

## $q是怎样的存在？
$q是一个延迟对象，延迟调用是实现promise的一种方式。  
调用resolve方法将会填充promise（即调用success处理函数）  
调用reject方法会调用promise的错误处理函数

	var delay = $q.defer()
	delay.resolve(arg)
	delay.reject(arg)

## What is Promise?
Promise是一个带有then()函数的对象，是一个接口。  
1. 可以对函数进行链式调用，不会陷入代码缩进噩梦之中。  
2. 在调用链的过程中，可以保证上一个函数调用完成之后才调用下一个函数。  
3. 每一个then()调用都带有两个参数（均为函数）。第一个是成功之后的回调，第二个是出错之后的处理器。  
4. 如果调用链中出现了错误，错误将会被冒泡传递到其余的错误处理函数中。  
所以，最终来说，所有的错误都可以在任意一个回调函数中进行处理。

## $q和Promise有什么关联？如何使用它们？

## .run和.config在语义上有何不同？

## 指令 directives

## 监控器 $on

## $httpProvider服务

## ngResource是个啥？

## $location服务
是对所有浏览器中都存在的window.location对象的封装。  
何时需要？1-需要对URL的变化做出相应的情况；2-需要针对浏览器当前的URL触发一次change事件的情况。    
$location.path('path')  
$location.url()  
$location.absUrl()  
$location.hash()  
$location.host()  
$location.protocol()  
$location.search()  

## $apply

## AngularJS Module
1. __config(configFn)__  
利用该方法可以做一些注册工作，这些工作需要在模块加载时完成
2. __constant(name, object)__  
此方法会首先运行，可以用来声明整个应用范围内的常量，并且让它们在所有配置和实例方法中可用
3. __controller(name, constructor)__  
控制器
4. __directive(name, directiveFactory)__  
指令  
5. __filter(name, filterFactory)__  
过滤器
6. __run(initializationFn)__  
如果你想要在注射器启动之后执行某些操作，而这些操作需要在页面对用户可用之前执行，可以使用此方法
7. __value(name, object)__  
8. 允许在整个应用中注射值
8. __service(name, serviceFactory)__  
9. __factory(name, factoryFn)__  
10. __provider(name, providerFn)__  

## 在不同作用域之间交互
每个Angular应用或者ng-app只有一个主作用域$rootScope，其他所有作用域都会继承这个主作用域。  
通常情况下，作用域之间不会共享变量，并且互相之间不会基于原型继承。  

1. __$on__  

2. __$emit__  

3. __$broadcast__  

## 在浏览器测试service方法
	var a = $h.ng.service('ServiceName');
		a.functionName();

## 使用Service暂存数据-hcx
    .factory('hcxService', function() {
        // 比如说，你想暂存一个变量，那可以这么写
        // 先在service作用域内定义这个变量
        var temp;

        // 向外暴露两个接口，一个接口用作获取这个变量（get），一个接口用作修改这个变量（set）
        return {
            getTemp: function() {
                return temp;
            },

            setTemp: function(value) {
                temp = value;
            }
        }
    })

    .controller('hcxController', function(hcxService) {
        // 调用时，先注入服务
        // 如需要将值存进temp变量中，调用setTemp方法即可
        hcxService.setTemp('123');

        // 如果需要取temp变量值，则调用getTemp方法
        var target = hcxService.getItem();

        console.log(target);
        // 123

    })



## 假数据创造
	.factory('TypeService', ['$http', '$q', '$templateRequest',
		function ($http, $q, $templateRequest) {
	
			return {
				getQuotaList: function () {
					return $q.when()
						.then(function () {
							return $templateRequest('./mock.json');
							})
	                    .then(function (mockStr) {
	                        var mock = JSON.parse(mockStr);
	                        return mock.quotaList;
	                        })
	            },
	            getTypeList: function () {
	                return $q.when()
	                    .then(function () {
	                    	return $templateRequest('./mock.json');
	                        })
	                    .then(function (mockStr) {
	                        var mock = JSON.parse(mockStr);
	                        return mock.typeList;
	                        })
                }
            }
        }
    ])