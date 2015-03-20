* **1. 半透明**

	* **方法一：** 怪异定位


	```
	div{
		background-color:rgba(0,0,0,0.6);//标准浏览器
		background-color: #000\9;  //CSS Hack,只能对ie9以下浏览器ie6,ie7,ie8有效
		opacity: 0.6;  //低版本的火狐
		filter: Alpha(opacity=60);/*只对ie7,ie8有效*/
	}
	div *{
		position:relative;//或者position:absolute;
	}
	```
	
	* **方法二：** 分层设置，通过定位和z-index
	


* **2. 图片垂直居中**

	* **方法一：淘宝图片处理**
	
		```
		div{
			/*标准浏览器*/
			display:table-cell;
			vertical-align:middle;
			/*水平居中*/
			text-align:center;
			/*ie hack*/
			*font-size:175px;   /*约为高度的0.873，200*0.873 约为175*/
			*font-family:Arial;   /*防止非utf-8引起的hack失效问题，如gbk编码*/
			width:200px;
			height:200px;
		}
		div img{
			vertical-align:middle;
		}
		```
		
	* **方法二：大小不固定，多行文字垂直居中**
	
		```
		div{
			display:table-cell;
			width:500px;
			height:114px;
			font-size:1000px;  //外部div高度和文字大小比例1.14
			vertical-align:middle;
		}
		div span{
			display:inline-block;
			vertical-align:middle;
			font-size:14px;
		}
		```
		
	* **方法三：**

* **3. 图片自适应大小**


* **4. 清除浮动**

* **5. 垂直对齐**

	```
	.box{
		position:relative;
		top:50%;
		-webkit-transform:translateY(-50%);
		-o-transform:translateY(-50%);
		-ms-transorm:translateY(-50%);
		transform:translateY(-50%);
	}
	```
	
	> 浏览器支持：Chrome 4, Opera 10, Safari 3, Firefox 3, Internet Explorer 9。
	
* **6. 元素拉伸为全屏高度**

	```
	html,body{
		height:100%;
	}
	.box{
		height:100%;
	}
	```
	
* **7. 根据不同的格式引用不同样式**

	```
	a[href^="http://"]{
		color:#333;
	}
	a[href^="mailto:"]{
		color:#f90;
	}
	a[href$=".pdf"]{
		color:#0097e0;
	}
	```
	```
	input[type=color], 
	input[type=date], 
	input[type=datetime-local], 
	input[type=datetime], 
	input[type=email], 
	input[type=month], 
	input[type=number], 
	input[type=password], 
	input[type=search], 
	input[type=tel], 
	input[type=text], 
	input[type=time], 
	input[type=url], 
	input[type=week]{
	}
	```

* **8. 表格自动调整列宽**

	```
	td{
		word-break:break-all;
	}
	```
	
* **9. css制作动画省略号**

	省略号
	
	```
	p{
		overflow: hidden;
		white-space: nowrap;   //规定段落中的文本不进行换行：
		text-overflow: ellipsis;
	}
	```
	> 火狐下没有ellipsis，可以用如下解决
	
	```
	p:after{
		content:"...";  
	}
	```
		
	动态省略号

	```
	p:after{
		overflow: hidden;
		display: inline-block;
		vertical-align: bottom;
		animation: ellipsis 2s infinite;
		content: "\2026"; 
	}
	@keyframes ellipsis {
		from {
			width: 2px;
		}
		to {
			width: 15px;
		}
	}
	```



	