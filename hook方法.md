## hook方法

#### js有三种方法

1.覆盖原函数
function xxx(){
	console.log('1111')
}
xxx=funtion(){
	console.log('2222')
}

2.使用一个中间变量，使两个函数都还能运行
function xxx(){
	console.log('1111')
}
var xxxx=xxx;
xxx=funtion(){
	console.log('2222')
}

可不可以覆盖浏览器环境的方法：
	window.alert=function(){console.log('答案是可以的')}



#### 2.可以通过Object.defineProperty替换一个对象的属性，属性里面存的可能是方法，也可能存的就是一个值（getter，setter）。

(function() {
	var cookieTemp = "";
    Object.defineProperty(document, 'cookie', { 
		set: function(val) {
				console.log(val)

​				cookieTemp = val

​				return val;
​		},
​		get: function()
​		{
​			return cookieTemp;
​		}
​    });
})();

#### 3.new Proxy

## HOOK的时机

1.在控制台注入的hook，刷新网页就失效了，在网页加载第一个js的位置，第一行下断点，然后在控制台手动注入hook（有可能注入hook的时机还是会晚一点）

2.利用FD的替换响应，注入hook


不拉不拉不拉
