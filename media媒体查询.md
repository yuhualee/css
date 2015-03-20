* 响应式设计的基础

* 媒体查询

	* 媒体查询包含一个媒体类型，后跟一个或多个检查特定条件（如最小的屏幕宽度）的表达式。
	
		```
		@media all and (min-width: 320px) and (max-width: 480px) and (orientation:portrait) { ... }
		```
	
		* all: 将此 CSS 应用于所有媒体类型。
	
		* (min-width:800px): 是包含媒体查询的表达式
	
		* orientation: 检查特定的屏幕方向，landscape（横向模型的apple ipad）,portrait(纵身模式)
		
			> iPad 上使用的是 orientation 媒体特性，而 width 用于 Apple iPhone 之上。主要是因为 iPhone 不支持 orientation 媒体特性。您必须使用 width 模拟这些方向断点。
	
		```
		@media (min-width:800px) or (orientation:portrait) { ... }
		```
	
		```
		@media (not min-width:800px) { ... }
		```
	
	* 也可以这样写
	
		```
		<link rel="stylesheet" href="./css/mobile.css" media="handheld and (max-width: 480px)">
		```
		
	* Media Type
	
		 类型        |   说明  
		 ---------- | ---------
		 all        | 所有设备
		 braille    | 盲人用点字法触觉反馈装置
		 embossed   | 盲文打印
		 handheld   | 手持设备
		 print      | 文档打印或打印预览模式
		 projection | 项目演示，如投影机、幻灯
		 screen     | 不分页的计算机屏幕
		 speech     | 演讲
		 tty        |   
		 tv         |   
		 
	
		 
* 浏览器支持

	* IE 9- 不支持
	* Firefox 3.5+ 支持
	* Opera 9.5+ 完全支持
	* Opera mini 5 支持
	* webkit 支持（chrome 5+ 开始支持, safari 3+ 开始支持）
	* iPhone 4 开始支持 orientation 属性

* sass中的媒体查询

	SASS 行为中的媒体查询与普通 CSS 中的完全相同，但有一个例外：它们可以嵌套在其他 CSS 规则中。当一个媒体查询嵌套在另一个 CSS 规则中时，会将规则置于样式表的顶层，如下：


	```
	#header {
  		width: 400px;
  		@media (min-width: 800px) {
    		width: 100%;
	    }
	}
	```

		 
		 
		 
	
		