[CSS样式分离之再分离](http://www.zhangxinxu.com/wordpress/2010/07/css%E6%A0%B7%E5%BC%8F%E5%88%86%E7%A6%BB%E4%B9%8B%E5%86%8D%E5%88%86%E7%A6%BB/)

[css样式合并与模块化](http://www.zhangxinxu.com/wordpress/2010/07/css%E7%9A%84%E6%A0%B7%E5%BC%8F%E5%90%88%E5%B9%B6%E4%B8%8E%E6%A8%A1%E5%9D%97%E5%8C%96/)



## 面向对象的css

* #### oo css的作用和注意事项

	* ##### 作用
	
		1. 加强代码利用方便维护
		
		* 减小css体积
		
		* 提升渲染效率
		
		* 组件库思想、栅格而已可共用、减少选择器、方便扩展
		
	* ##### 注意注意事项

		1. 不要直接定义子节点，应把共性声明放到父类
		
			```
			.mod{
				//设置共性，比如 font-size、color...
			}
			.mod .inner{
				...
				//单独设置的内容
			}
			```
	
		* 结构和皮肤相分离
	
			```
			<div class="container simpleExt"></div> 
			```
			
			```
			.container{
				//布局代码
			}
			.simpleExt{
				//皮肤代码
			}
			```
			
		* 容器与内容相分离
		
			```
			<div class="container">
				<ul>
					...
				</ul>
			</div>
			.container ul{
				//容器依赖，不合理
			}
			```
			```
			<div class="container">
				<ul class="list">
					...
				</ul>
			</div>
			.list{
				//解决容器依赖，放哪里都行
			}
			```
				
		* 抽象出可重用的元素，建好组件库，在组件库内寻找可用的元素组装页面
		
		* 而你想要扩展的对象本身增加class而不是他的父节点。
		
		* 对象应保持独立性。
		
		* 避免使用ID选择器，权重太高，无法重用。
		
		* 保持选择器相同的权重。
		
		* 类名 简短 清晰 语义化 oocss的名字并不影响html语义化。
		
	* ##### oo css实战 
	
		[oo css](http://oocss.org/)