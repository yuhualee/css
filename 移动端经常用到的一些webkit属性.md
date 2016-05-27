

* **-webkit-tap-highlight-color:**

	当用户点击IOS的Safari浏览器中的链接或javascript的可点击元素时，覆盖显示的高亮颜色。
	
	该属性可以只设置透明度。如果未设置透明度，iOS Safari使用默认的透明度。当透明度设为0，则会禁用此属性；当透明度设为1，元素在点击时不可见。
	
	
	```
	-webkit-tap-highlight-color: rgba(0,0,0,0);
	```
	
* **-webkit-line-clamp:**

	限制在一个块元素显示的文本的行数。需要结合其它属性来实现：

	```
	display:-wekbit-box;    //将对象作为弹性伸缩盒子模型显示
	-webkit-box-orient: vertical;   //设置或检索伸缩盒对象的子元素的排列方式
	text-overflow: ellipsis;   
	-webkit-line-clamp: 2;    //超过2行隐藏
	overflow:hidden;
	```
	
* **-webkit-appearance**

	改变按钮和其他控件的外观，使其类似于原生控件。


	```
	-webkit-appearance：none | button | button-bevel ....
	-webkit-appearance: none;   //去除系统默认appearance的样式,常用于IOS下移除原生样式
	```                           
	
	









