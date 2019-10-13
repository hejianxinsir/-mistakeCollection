- 会动的简历那个代码。要给 '#resumePaper > .content' 宽高，在 js 里设置的 domCode.scrollTop = domCode.scrollHeight 才会自动滑动到底部。

```
// CSS

#resumePaper > .content{
	width: 100%;
	height: 100%;
	overflow: auto;
}

// JS

function writeMarkdown(markdown, fn){
	var n = 0
	var domCode = document.querySelector('#resumePaper > .content')
	var id = setInterval(function(){
		domCode.innerHMTL = markdown.slice(0,n)
		domCode.scrollTop = domCode.scrollHeight

		if(n >= markdown.length){
			window.clearInterval(id)
			fn && fn.call
		}
	},10)
}

// 另外 domCode.scrollTop = 10000 也可以，效果是一样的。
```
