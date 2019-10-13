- 做会动的简历，把 prefix 误写成了 ‘’ 空字符串。导致找了半天错误，很抓狂。正确写法是这样的：
```
// 封装一个函数
```
function writeCode(prefix, css, fn){
	var n = 0
	var leftCode = document.querySelector('#leftCode')
	var styleCode = document.querySelector('#styleCode')
	var id = setTimeout(function fnTime(){
		n += 1
		leftCode.innerHTML = css.slice(0,n)
		styleCode.innerHTML = css.slice(0,n)
		if( n < css.length){
			setTimeout(fnTime,100)
		}
		fn && fn()
	},100)
}
```
