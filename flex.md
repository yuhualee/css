## flex属性

1. 属性

	* flex container

		* flex
		
			```	
			display:flex;   //块元素
			display:inline-flex;    //行内元素
			```
			
		* flex-flow: <flex-direction> || <flex-wrap>
		
			* flex-direction

				```
				flex-direction: row | row-reverse | column | column-reverse
				```			
			
			* flex-wrap
			
				```
				flex-wrap: nowrap | wrap | wrap-reverse
				```
			
		* justify-content
					
			```
			justify-content: flex-start | flex-end | center | space-between | space-around
			```
			居左 | 居右 | 居中 | 两端对齐 | 中间平分
			
		* align-items
		
			```
			align-items: flex-start | flex-end | center | stretch | baseline
			```
			
			靠上 | 靠下 | 垂直居中 | 高度填充满 | 文字baselines对齐 
			
		* align-content: 多行情况
		
			```
			align-content: flex | flex-end | center | stretch | space-between | space-around
			```
			靠上 | 靠下 | 垂直居中 | 上下对齐高度拉伸 | 上下对齐，高度不变 | 上下平分 
		
	* flex items
	
		* flex
	
			```
			flex:1;
			```
			
		
		
		* margin，padding, border 
	
			* margin：相邻不合并
			* padding, border: flex分配比例里面不包含


* Demo

	* html

		```
		<ul class="flex-mul">
			<li class="flex-item">普通item</li>
			<li class="flex-item">普通item</li>
			<li class="flex-item flex-big"></li>
			<li class="flex-item">普通item</li>
			<li class="flex-item"><p>我是最后一个item，我使用了order:-1</p></li>
		</ul>
		```

	* css

		```
		.flex-mul{
			display: flex;    /*弹性布局，使子项目等高*/
			flex-flow:row wrap;    /*允许子项目显示多行，一行放不下时，自动换行*/
			width: 300px;
			box-sizing:border-box;
		}
		.flex-mul .flex-item{
			width: 100px;
			border: 1px solid #ccc;
		}
		.flex-mul .flex-big{
			width: 150px;
		}
		.flex-mul .flex-item:last-child{
			order: -1;   /*把它显示在其他内容（在视觉顺序）之前*/
		}
		```


---

## flex布局

1. html

	```
	<ul class="flex-container">
		<li class="flex-item flex1">我会占剩余的三分之一，不包含padding和border</li>
		<li class="flex-item flex2">我会占剩余的三分之二，不包含padding和border</li>
		<li class="flex-item flex-none">无论窗口如何变化，我的宽度一直是150px。</li>		<li class="flex-item flex1">我会占剩余的三分之一，不包含padding和border</li>
		<li class="flex-item initial">空间足够的时候，我的宽度是150px，如果空间不足，我会变窄到100px，但不会再窄了。</li>
	</ul>
	```

* css

	```
	.flex-container{
		list-style: none;
		display:-webkit-flex;
		display: flex;
	}
	.flex-container .flex-item{
		padding: 5px;
		margin:5px;
		border: 1px solid #ccc;
	}
	.flex-container .flex-item:nth-child(4){
		min-width:80px;  //最小宽度
	}
	.flex1{
		-webkit-flex:1;
				flex:1;
	}
	.flex2{
		-webkit-flex:2;
				flex:2;
	}
	.initial{
		-webkit-flex:initial;
				flex:initial;
		width: 150px;
	}
	.flex-none{
		-webkit-flex:none;
				flex:none;
		width: 150px;
	}
	```
	> **注意：**  
	
	>  * 例如宽度是1：2，这个宽度是指里面内容的宽度，不包含padding和border。即便设置了`box-sizing:border-box`，它的宽度仍然不包含。
	  
	> * margin： 如果item有margin，那么相邻的margin不合并。


----

## flex居中布局

1. html

	```
	<div class="vertical-container">
		<p class="text">这是居中显示么？flex垂直居中</p>
	</div>
	```
	
* css

	```
	.vertical-container{
		height: 300px;
		display: -webkit-flex;
				display: flex;
		-webkit-align-items:center;
				align-items:center;
		-webkit-justify-content:center;
				justify-content:center;
	}
	.vertical-container .text{
		border: 1px solid #ccc;
	}
	```

---

## flex兼容性

1. 兼容性及版本

	```
	display: -webkit-box;
	display: -moz-box;
	display: -ms-flexbox;
	display: -webkit-flex;
	display: flex;
	```
	> * `display:box` 2009年的版本
	* `display:flexbox` 2011年的版本
	* `display:flex` 当前的版本
	


---

https://css-tricks.com/snippets/css/a-guide-to-flexbox/

https://css-tricks.com/almanac/properties/f/flex-flow/

http://css.doyoe.com/

https://css-tricks.com/almanac/properties/f/flex/

http://www.zhangxinxu.com/wordpress/2010/12/css-box-flex%E5%B1%9E%E6%80%A7%EF%BC%8C%E7%84%B6%E5%90%8E%E5%BC%B9%E6%80%A7%E7%9B%92%E5%AD%90%E6%A8%A1%E5%9E%8B%E7%AE%80%E4%BB%8B/

http://www.w3school.com.cn/cssref/pr_box-flex.asp

https://bocoup.com/weblog/dive-into-flexbox/


参考： [flex](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)



