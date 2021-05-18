##  HTML 学习总结
>
### 前言
痛苦的时光总会抹去，明天又是美好的一天。
>
### 理论知识

#### 1、如何理解 HTML？
* 描述文档的 &ldquo; 结构 &rdquo;
* 有区块和大纲（算法）

#### 2、HTML 版本发展？
* HTML 4 / 4.0 （SGML)
* XHTML (XML)
* HTML5

#### 3、HTML 语义化的意义？
* 有利于开发者理解，容易阅读维护
* 页面内容结构化，便于对搜索引擎解析
* 有利于搜索引擎的爬虫依赖标记确定上下文及各个关键词的权重，有利于 `SEO`

#### 4、Doctype 的意义？标准模式和兼容模式的区别？
* 声明位于文档中的最前面，告知浏览器的解析器，用什么文档类型规范来解析这个文档
* 让浏览器知道元素的合法性（浏览器具有一定的容错能力）
* 标准模式的排版和 js 运行模式都是以浏览器支持的最高标准运行。
* 在兼容模式中，页面以宽松的向后兼容的方式显示，模拟老式浏览器的行为以防止站点无法工作

#### 5、HTML 元素分类？
* 按默认样式
	* 块级元素 `block` : h1-h6 section div p ul ol li dl dt dd &hellip;
	
         ```可以设置宽高，独占一行，有规则形状```

	* 行内元素 `inline` : span img em a b strong &hellip;
	
		```不可以设置宽高，不一定有规则形状```

	* 内联块级元素 `inline-block` : select img
	
		```对内 block 有尺寸；对外 inline 不换行```

* HTML5 新增元素的内容模型 `Content Model`
	* Metadata
	* Flow
	* Sectioning
	* Heading
	* Phrasing
	* Embedded
	* Interactive


    参考 [查看内容模型](http://www.w3.org/TR/html5/dom.html#content-models)

#### 6、HTML 元素嵌套关系？
* 块级元素可以包含行内元素

* 块级元素不一定可以包含块级元素

* 行内元素一般不能包含块级元素（取决于它的父级元素）

		<!--这是一个 a 包含 div 不合法的例子-->
		<p>  <!--因为 div 不属于 p 的 Phrasing content ，所以 p 包含 div 不合法-->
			<a href="#"> <!--这里 a 属于 transparent，相当于只需考虑 p 包含 div 的合法性-->
				<div>这是div</div>
			</a>
		</p>
参考 [查看 p 元素的 Content model](https://html.spec.whatwg.org/multipage/dom.html#phrasing-content-2)
#### 7、HTML 新增的内容？
* 新区块标签
> header nav main section article aside footer &hellip;

* 表单增强
> 日期、时间、搜素、表单验证、placeholder 自动聚焦 &hellip;

* 标签语义化
> header/footer section/article nav aside em/strong &hellip;

* 新的 API
> 离线、音视频、图形、实时通信、设备能力（地图定位） &hellip;

* 分类和嵌套变更

#### 8、哪些元素可以自闭和？
* 表单元素 `input`
* 图片 	`img`
* br hr meta link &hellip;

#### 9、对于em 和 i 的理解？
* 两个默认样式为斜体
* `em` 是语义化标签，表强调
* `i` 表示一块不同于其它文字的文字，具有不同的语态和语气

#### 10、from 的作用有哪些？
* 直接提交表单
* 使用 `submit` / `reset` 按钮
* 便于浏览器保存表单
* 第三方库可以进行整体提取值，可以进行表单验证

#### 11、img 的 title 和 alt 有什么区别？
* `alt` 是图片加载失败时，显示在网页上提供的文字说明
* `title` 提供建议性的信息，可以实现鼠标悬停提示的效果
*  `alt` 是 `img` 必要的属性，而 `title` 不是

#### 13、元素的title属性对语义的重要性是什么？
* 具有提示作用，对于屏幕阅读器可以为用户朗读文本
* 正确的使用可以提升页面的访问性 

#### 14、em 和 strong 的区别？
* `em` 表示强调文本，默认为斜体
* `strong` 表示的是重要的文本，默认为粗体显示，良好的语义性可以更好的与用户交互

#### 15、对于 div 和 span 的理解？
* `div` 全拼是 division，块级容器，本身没有任何的语义，但可以为它增加 CSS 样式。 通常情况下我们要使用语义化的标签，但如果没有任何一个语义化标签可用于我们需要的语义，可以使用它。
* `span` 与 `div` 用法相似，只是它是短语的无语义容器

#### 16、简述 src 和 href 的区别？
* `src` 用于替换当前元素；`href` 用于在当前文档和引用资源之间确立关系
* `src` 是 source 的缩写，指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在的位置
* `href` 是 Hypertext Reference 的缩写，指向网络资源所在的位置，建立和当前元素（锚点）或当前文档之间的链接

#### 17、简述 table 的缺点？
* 嵌套层级太深，会导致搜索引擎读取困难，而且会大大增加代码冗余
* 灵活性差，比如要设置 `tr` 的 `border` 等属性是不行的，要在 `td` 上设置 `border` 属性
* 代码臃肿，可读性差
* 混乱的 `colspan` 和 `rowspan`, 用它们来实现网页布局时，会造成文档顺序混乱
* 不够语义化 

### 学习案例

#### 1、段落与文字
	<body>
		1、标题标签
		<h1>header一共有6个级别，一般只有一个h1,其作用关注SEO</h1>
		
		2、段落标签
		<p>paragraph段落内容，自动换行，段落与段落之间有空隙</p>
		
		3、文本标签<br />
		<b>加粗</b>
		<strong>加粗</strong><!--更具有语义性-->
		<i>斜体</i>
		<cite>斜体</cite>
		<em>emphasized斜体</em><!--使用这个居多-->
		a<sup>superscripted上标</sup>
		b<sub>subscripted下标</sub>
		<big>大字号文本</big>
		<small>小字号文本，常用于网页底部的版权声明</small>
		<s>删除线，常用于商品标价</s>
		<!--css中一般采用text-decoration:line-through;实现-->
		<u>下划线标签</u>
		<!--css中一般采用text-decoration:underline;实现-->
		<div>division分区，使代码更具有逻辑性，方便css样式控制</div>
	
		<br />
		4、换行标签<!--自闭和标签-->
		<br />break换行，两端之间没有空隙<br />
		
		5、水平线标签<br /><!--自闭和标签-->
		<hr />horizontal rule水平线
		
		<!--常见的自闭和标签-->
		<meta />
		<link rel="stylesheet" href="" />用于连接外部的css文件或脚本文件
		<base href="" />定义页面所有链接的基础定位
		<input type="" name="" id="" value="" />
		<img src=""/>
		<br />
		
		6、特殊符号
		首行缩进&nbsp;
		<!--css中一般采用text-index:值+单位;实现-->
		与符号&amp;
		常破折号&mdash;
		竖线&#124;
		<!--两种方法显示特殊字符-->
		<p>欧元符号：&euro;</p>
		<p>欧元符号：€</p>
		
		7、块元素block,矩形，独占一行，可以容纳行元素和其他的块元素
		div h1-6 p hr br ol  ul
		
		行内元素inline，相邻两个行内元素可以位于同一行，不可以容纳块元素
		strong em s u a span常用行级  img input表单
		
		8、其它
		<ruby>在文字上方标注说明<rt>2020</rt></ruby>
		<br>
		地址：<adress>xxx@mail.com</adress>
		<p><tt>武汉加油，中国加油</tt></p><!--设置等宽文字-->
		<pre>预格式化标签</pre>
		<blockquote><p>文字前后换行有缩进</p></blockquote>

	</body>

#### 2、表单
	<body>
	    <fieldset>
	       <legend>测试 input type属性值，自闭和标签</legend>
	       <form  name="myForm1" method="post" action="01.html" enctype="multipart/form-data">
		   <h4>text <input type="text" id="wenb" value="定义文本框的默认值（文字）" size="定义文本框的长度，单位字符" maxlength="最多输入的字符数"> </h4>
		   <h4>password <input type="password" /></h4>
		<!--注意：其他属性与text类似，为了数据安全需要在浏览器和服务器之间建立一个安全链接-->
		   <h4>search <input type="search"> </h4>
		   
		   <h4>week/month <input type="month"> </h4>
		   
		   <h4>date <input type="date"> </h4>
		   <h4>datetime<input type="datetime"> </h4>
		   
		   
		   <h4>range <input type="range"> 滑块组件</h4>
		   
		   <h4>time <input type="time"> </h4>
		   <h4>url <input type="url"> </h4>
		   <h4>radio 
		   	<input type="radio" name="question1" value="boy"/>男
		    <input type="radio" name="question1" value="girl"/>女
		   </h4>
		<!--注意：对于同一个问题的不同选项，必须要设置一个相同的name属性值，这样才能把这些选项归为同一个问题。value的作用在于为了方便向服务器端传递数据-->
	       <h4>checkbox 多选 
	       	<input  id="checkbox1" type="checkbox" checked /><label for="checkbox1">苹果</label> 
	       	<input  id="checkbox2" type="checkbox"  /><label for="checkbox2">香蕉</label> 
	       	<input  id="checkbox3" type="checkbox"  /><label for="checkbox3">西瓜</label> 
	       	<input  id="checkbox4" type="checkbox"  /><label for="checkbox4">凤梨</label> 
	       </h4>
	    <!--注意：复选框checkbox和label标签配合使用，虽然单独使用实现效果类似-->
		   <h4>color <input type="color"> </h4>
		   <h4>email <input type="email"> </h4>
		   
		   
		   <h4><input type="image" src="图片的路径" />这是图片域  </h4>
		<!--注意：尽量用css来模拟实现，这是因为图片往往数据传输量大，影响页面加载速度-->  
		   <h4>hidden <input type="hidden" value="10">这是隐藏域</h4>
		   <h4>file <input type="file">这是文件域</h4>
		<!--注意：必须设置form的enctype="multipart/form-data"-->
		
		   <h4>button <input type="button" value="按钮取值" onclick="alert('这是js脚本程序')"> </h4>
		<!--注意：onclick是普通按钮的事件-->
		   <h4>reset <input type="reset" value="重"> </h4>
		<!--注意：value默认为"重置"，清除的是文本框的文本内容，而不是清除css样式，
			针对当前所在form标签而言的。
		-->  
		   <h4>submit<input type="submit" value="交">表单内容提交给服务器</h4>
		<!--注意：value默认为"提交"，
			针对当前所在form标签而言的。
		-->
		   </form>
		</fieldset>
		
		<from name="myForm2" method="post" action="01.html">
		   	个人简介：<br />
		   	<textarea name="textarea1" rows="8" cols="40">请简绍一下你自己</textarea>
		</from>
		<h4>下拉列表select</h4>
		<select name="">
			<option value="">html</option>
			<option value="" selected >css</option>
			<option value="" >js</option>
		</select>
	<!--注意：multiple="multiple"表示可选择多个值，size="3"是可见列表项的数目，不同的浏览器样式不同-->
		<br />
		<button>这是一个button标签可插入文本或其他标签</button>
	</body>
#### 3、常用结构标签
	<body>
		<header>页头</header>
		<nav>导航</nav>
		<section>主体内容</section>
		<aside>广告侧边栏</aside>
		<footer>页脚</footer>
	</body>
#### 4、音视频标签
	<body>
		<vedio src="地址" controls autoplay loop>视频不支持显示</vedio>
		<audio src="地址" controls autoplay loop muted>音乐不支持显示</audio>
		<!--
        	autoplay ---自动播放（谷歌限制）
        	loop ---循环
        	controls ---控件显示
        	muted ---静音(视频标签在静音状态下即可实现视频播放)
        -->
	</body>
