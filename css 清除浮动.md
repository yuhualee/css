* **方法一：使用带clear属性的空元素**

	添加无意义的标签，不好。


	html:
	
	```
	<div class="fl"></div>
	<div class="fr"></div>
	<div class="clear"></div>
	```
	css:

	```
	.clear{clear:both;}
	```
	
* **方法二：使用css的overflow属性**

	给浮动元素的容器添加overflow:hidden;或overflow:auto;可以清除浮动，另外在 IE6 中还需要触发 hasLayout ，例如为父元素设置容器宽高或设置 zoom:1。
	
	```
	.clear{
		overflow:hidden;
		*zoom:1;
	}
	```
	
* **方法三：给浮动的元素的容器添加浮动**

	给浮动元素的容器也添加上浮动属性即可清除内部浮动，但是这样会使其整体浮动，影响布局，不推荐使用。

	html:

	```
	<div class="fl">
		<div class="fl">子元素</div>
	</div>
	```

* **方法四：使用邻接元素处理**

	跟方法一，其实很像。


	html:
	
	```
	<div class="fl"></div>
	<div class="fr"></div>
	<div class="content">
		这是后面的元素
	</div>
	```
	css:

	```
	.clear{clear:both;}
	```	
* **方法五：使用CSS的:after伪元素**

	结合 :after 伪元素（注意这不是伪类，而是伪元素，代表一个元素之后最近的元素）和 IEhack ，可以完美兼容当前主流的各大浏览器，这里的 IEhack 指的是触发 hasLayout。

	给浮动元素的容器添加一个clearfix的class，然后给这个class添加一个:after伪元素实现元素末尾添加一个看不见的块元素（Block element）清理浮动。


	html:
	
	```
	<div class="content clearfix">
		<div class="fl"></div>
		<div class="fr"></div>
	</div>
	```
	
	css:
	
	```
	.clearfix{
		zoom: 1; //触发haslayout
	}
	.clearfix:after{
		content: '020';
		display:block;
		height:0;
		clear: both; 
	  	visibility: hidden; 
	}
	```
	> 通过CSS伪元素在容器的内部元素最后添加了一个看不见的空格"020"或点"."，并且赋予clear属性来清除浮动。需要注意的是为了IE6和IE7浏览器，要给clearfix这个class添加一条zoom:1;触发haslayout。

* **方法五：最精简**

	```
	.clearfix:before,
	.clearfix:after{
		content: '';
		display:table;
	}
	.clearfix:after{
		clear:both;
	}
	.clearfix{
		zoom:1; // For IE 6/7 (trigger hasLayout)
	}
	```






