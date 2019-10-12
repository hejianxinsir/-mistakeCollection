1. 所有 setInterval 都可以用 setTimeout 代替
```
var n = 0
var id = setInterval(function(){
	n += 1
	leftCode.innerText = n
	if(n >= 10){
		window.clearInterval(id)
	}
},500)

// 替换如下：

var n = 0
setTimeout(function fn(){
	n += 1
	leftCode.innerText = n
	if(n<10){
		setTimeout(fn,500)	// 尤其注意这里。这里的 fn 是没有 () 的，在这里错过
	}
},500)
```
