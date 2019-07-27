# interview
# 每日三问——0425
> [github项目](https://github.com/haizlin/fe-interview?utm_source=ZHShareTargetIDMore&utm_medium=social&utm_oi=750848792785354752) 问题解答
# HTML
### 浏览器内多个标签页之间的通信方式有哪些？
> [ https://xv700.gitee.io/message-communication-for-web/ ](https://xv700.gitee.io/message-communication-for-web/)
# CSS
### 简述下你理解的优雅降级和渐进增强
* 优雅降级：先发布最新浏览器的可运行版本，再向低版本兼容
* 渐进增强：以内容为主，先向低版本浏览器做兼容性处理，再完善新版本浏览器内容支持
# JS
### 写一个判断数据类型的方法
* 通过toString方法判断
```javascript
function myTypeof(origin){
	return Object.prototype.toString.call(origin).replace(/(\[object)|\]/g,"")
}		
```
* 上述方法无法判断new对象，可封装以下方法判断所有情况
```javascript
function myTypeof(origin){
	var result = {
		"[object String]" : "[object String]",
		"[object Number" : "[object Number]",
		"[object Array]" : "Array",
		"[object Object]" : "Object",
		"[object Boolean]" : "[object Boolean]"
	}
	if (typeof origin === "object"){
		if(origin === null){
			return "null";
		}else{
			var str = Object.prototype.toString.call(origin);
			return result[str];
		}
	}else{
		return typeof origin;
	}
}
```