介绍一下标准的CSS的盒子模型？低版本IE的盒子模型有什么不同的？

  （1）有两种， IE 盒子模型、W3C 盒子模型；
  （2）盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border)；
  （3）区  别： IE的content部分把 border 和 padding计算了进去;
CSS选择符有哪些？哪些属性可以继承？

  * 1.id选择器（ # myid）
  	2.类选择器（.myclassname）
  	3.标签选择器（div, h1, p）
  	4.相邻选择器（h1 + p）
  	5.子选择器（ul > li）
  	6.后代选择器（li a）
  	7.通配符选择器（ * ）
  	8.属性选择器（a[rel = "external"]）
  	9.伪类选择器（a:hover, li:nth-child）

  *   可继承的样式： font-size font-family color, UL LI DL DD DT;

  *   不可继承的样式：border padding margin width height ;
CSS优先级算法如何计算？

  *   优先级就近原则，同权重情况下样式定义最近者为准;
  *   载入样式以最后载入的定位为准;

  优先级为:
  	同权重: 内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）。
  	!important >  id > class > tag
  	important 比 内联优先级高
CSS3新增伪类有那些？

  	举例：
  	p:first-of-type	选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
  	p:last-of-type	选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
      p:only-of-type	选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
  	p:only-child		选择属于其父元素的唯一子元素的每个 <p> 元素。
  	p:nth-child(2)	选择属于其父元素的第二个子元素的每个 <p> 元素。

  	:after			在元素之前添加内容,也可以用来做清除浮动。
  	:before			在元素之后添加内容
      :enabled  		
  	:disabled 		控制表单控件的禁用状态。
  	:checked        单选框或复选框被选中。
如何居中div？

水平居中：给div设置一个宽度，然后添加margin:0 auto属性

 div{
 	width:200px;
 	margin:0 auto;
  }
让绝对定位的div居中

 div {
 	position: absolute;
 	width: 300px;
 	height: 300px;
 	margin: auto;
 	top: 0;
 	left: 0;
 	bottom: 0;
 	right: 0;
 	background-color: pink;	/* 方便看效果 */
 }
水平垂直居中一

 确定容器的宽高 宽500 高 300 的层
 设置层的外边距

 div {
 	position: relative;		/* 相对定位或绝对定位均可 */
 	width:500px;
 	height:300px;
 	top: 50%;
 	left: 50%;
 	margin: -150px 0 0 -250px;     	/* 外边距为自身宽高的一半 */
 	background-color: pink;	 	/* 方便看效果 */

  }
水平垂直居中二

 未知容器的宽高，利用 `transform` 属性

 div {
 	position: absolute;		/* 相对定位或绝对定位均可 */
 	width:500px;
 	height:300px;
 	top: 50%;
 	left: 50%;
 	transform: translate(-50%, -50%);
 	background-color: pink;	 	/* 方便看效果 */

 }
水平垂直居中三

 利用 flex 布局
 实际使用时应考虑兼容性

 .container {
 	display: flex;
 	align-items: center; 		/* 垂直居中 */
 	justify-content: center;	/* 水平居中 */

 }
 .container div {
 	width: 100px;
 	height: 100px;
 	background-color: pink;		/* 方便看效果 */
 }  
display有哪些值？说明他们的作用。

    block       	块类型。默认宽度为父元素宽度，可设置宽高，换行显示。
    none        	缺省值。象行内元素类型一样显示。
    inline      	行内元素类型。默认宽度为内容宽度，不可设置宽高，同行显示。
    inline-block  默认宽度为内容宽度，可以设置宽高，同行显示。
    list-item   	象块类型元素一样显示，并添加样式列表标记。
    table       	此元素会作为块级表格来显示。
    inherit     	规定应该从父元素继承 display 属性的值。
position的值relative和absolute定位原点是？

    absolute
  	生成绝对定位的元素，相对于值不为 static的第一个父元素进行定位。
    fixed （老IE不支持）
  	生成绝对定位的元素，相对于浏览器窗口进行定位。
    relative
  	生成相对定位的元素，相对于其正常位置进行定位。
    static
  	默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right z-index 声明）。
    inherit
  	规定从父元素继承 position 属性的值。
CSS3有哪些新特性？

    新增各种CSS选择器	（: not(.input)：所有 class 不是“input”的节点）
    圆角		    （border-radius:8px）
    多列布局	    （multi-column layout）
    阴影和反射	（Shadow\Reflect）
    文字特效		（text-shadow、）
    文字渲染		（Text-decoration）
    线性渐变		（gradient）
    旋转		 	（transform）
    缩放,定位,倾斜,动画,多背景
    例如:transform:\scale(0.85,0.90)\ translate(0px,-30px)\ skew(-9deg,0deg)\Animation:
请解释一下CSS3的Flexbox（弹性盒布局模型）,以及适用场景？

   一个用于页面布局的全新CSS3功能，Flexbox可以把列表放在同一个方向（从上到下排列，从左到右）,并让列表能延伸到占用可用的空间。
   较为复杂的布局还可以通过嵌套一个伸缩容器（flex container）来实现。
   采用Flex布局的元素，称为Flex容器（flex container），简称"容器"。
   它的所有子元素自动成为容器成员，称为Flex项目（flex item），简称"项目"。
   常规布局是基于块和内联流方向，而Flex布局是基于flex-flow流可以很方便的用来做局中，能对不同屏幕大小自适应。
   在布局上有了比以前更加灵活的空间。
具体：http://www.w3cplus.com/css3/flexbox-basics.html

用纯CSS创建一个三角形的原理是什么？

  把上、左、右三条边隐藏掉（颜色设为 transparent）
  #demo {
    width: 0;
    height: 0;
    border-width: 20px;
    border-style: solid;
    border-color: transparent transparent red transparent;
  }
一个满屏 品 字布局 如何设计?

  简单的方式：
  	上面的div宽100%，
  	下面的两个div分别宽50%，
  	然后用float或者inline使其不换行即可
css多列等高如何实现？

  利用padding-bottom|margin-bottom正负值相抵；
  设置父容器设置超出隐藏（overflow:hidden），这样子父容器的高度就还是它里面的列没有设定padding-bottom时的高度，
  当它里面的任 一列高度增加了，则父容器的高度被撑到里面最高那列的高度，
  其他比这列矮的列会用它们的padding-bottom补偿这部分高度差。
经常遇到的浏览器的兼容性有哪些？原因，解决方法是什么，常用hack的技巧 ？

  * png24位的图片在iE6浏览器上出现背景，解决方案是做成PNG8.

  * 浏览器默认的margin和padding不同。解决方案是加一个全局的*{margin:0;padding:0;}来统一。

  * IE6双边距bug:块属性标签float后，又有横行的margin情况下，在ie6显示margin比设置的大。

    浮动ie产生的双倍距离 #box{ float:left; width:10px; margin:0 0 0 10px;}

    这种情况之下IE会产生20px的距离，解决方案是在float的标签样式控制中加入 ——_display:inline;将其转化为行内属性。
  		(_这个符号只有ie6会识别)

    渐进识别的方式，从总体中逐渐排除局部。

    首先，巧妙的使用“\9”这一标记，将IE游览器从所有情况中分离出来。
    接着，再次使用“+”将IE8和IE7、IE6分离开来，这样IE8已经独立识别。

    css
        .bb{
            background-color:red;/*所有识别*/
  	      background-color:#00deff\9; /*IE6、7、8识别*/
  	      +background-color:#a200ff;/*IE6、7识别*/
  	      _background-color:#1e0bd1;/*IE6识别*/
        }


  *  IE下,可以使用获取常规属性的方法来获取自定义属性,
     也可以使用getAttribute()获取自定义属性;
     Firefox下,只能使用getAttribute()获取自定义属性。
     解决方法:统一通过getAttribute()获取自定义属性。

  *  IE下,even对象有x,y属性,但是没有pageX,pageY属性;
     Firefox下,event对象有pageX,pageY属性,但是没有x,y属性。

  *  解决方法：（条件注释）缺点是在IE浏览器下可能会增加额外的HTTP请求数。

  *  Chrome 中文界面下默认会将小于 12px 的文本强制按照 12px 显示,
     可通过加入 CSS 属性 -webkit-text-size-adjust: none; 解决。

  超链接访问过后hover样式就不出现了 被点击访问过的超链接样式不在具有hover和active了解决方法是改变CSS属性的排列顺序:
  L-V-H-A :  a:link {} a:visited {} a:hover {} a:active {}
li与li之间有看不见的空白间隔是什么原因引起的？有什么解决办法？

  行框的排列会受到中间空白（回车\空格）等的影响，因为空格也属于字符,这些空白也会被应用样式，占据空间，
  所以会有间隔，把字符大小设为0，就没有空格了。
为什么要初始化CSS样式。

  - 因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。

  - 当然，初始化样式会对SEO有一定的影响，但鱼和熊掌不可兼得，但力求影响最小的情况下初始化。

  最简单的初始化方法： * {padding: 0; margin: 0;} （强烈不建议）

  淘宝的样式初始化代码：
  body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button,
  input, textarea, th, td { margin:0; padding:0; }
  body, button, input, select, textarea { font:12px/1.5tahoma, arial, \5b8b\4f53; }
  h1, h2, h3, h4, h5, h6{ font-size:100%; }
  address, cite, dfn, em, var { font-style:normal; }
  code, kbd, pre, samp { font-family:couriernew, courier, monospace; }
  small{ font-size:12px; }
  ul, ol { list-style:none; }
  a { text-decoration:none; }
  a:hover { text-decoration:underline; }
  sup { vertical-align:text-top; }
  sub{ vertical-align:text-bottom; }
  legend { color:#000; }
  fieldset, img { border:0; }
  button, input, select, textarea { font-size:100%; }
  table { border-collapse:collapse; border-spacing:0; }
absolute的containing block(容器块)计算方式跟正常流有什么不同？

  无论属于哪种，都要先找到其祖先元素中最近的 position 值不为 static 的元素，然后再判断：
  1、若此元素为 inline 元素，则 containing block 为能够包含这个元素生成的第一个和最后一个 inline box 的
  padding box (除 margin, border 外的区域) 的最小矩形；
  2、否则,则由这个祖先元素的 padding box 构成。
  如果都找不到，则为 initial containing block。

  补充：
  1. static(默认的)/relative：简单说就是它的父元素的内容框（即去掉padding的部分）
  2. absolute: 向上找最近的定位为absolute/relative的元素
  3. fixed: 它的containing block一律为根元素(html/body)，根元素也是initial containing block
CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下以后什么区别？

对于普通元素visibility:collapse;会将元素完全隐藏,不占据页面布局空间,与display:none;表现相同. 如果目标元素为table,visibility:collapse;将table隐藏,但是会占据页面布局空间. 仅在Firefox下起作用,IE7及以下会显示元素,Chrome会将元素隐藏,但是占据空间.

position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？

如果元素的display为none,那么元素不被渲染,position,float不起作用,如果元素拥有position:absolute;或者position:fixed; 属性那么元素将为绝对定位,float不起作用.如果元素float属性不是none,元素会脱离文档流,根据float属性值来显示.有浮动,绝对 定位,inline-block属性的元素,margin不会和垂直方向上的其他元素margin折叠.

对BFC规范(块级格式化上下文：block formatting context)的理解？

  （W3C CSS 2.1 规范中的一个概念,它是一个独立容器，决定了元素如何对其内容进行定位,以及与其他元素的关系和相互作用。）
   一个页面是由很多个 Box 组成的,元素的类型和 display 属性,决定了这个 Box 的类型。
   不同类型的 Box,会参与不同的 Formatting Context（决定如何渲染文档的容器）,因此Box内的元素会以不同的方式渲染,
   也就是说BFC内部的元素和外部的元素不会互相影响。
css定义的权重

  以下是权重的规则：标签的权重为1，class的权重为10，id的权重为100，以下例子是演示各种定义的权重值：

  /*权重为1*/
  div{
  }
  /*权重为10*/
  .class1{
  }
  /*权重为100*/
  #id1{
  }
  /*权重为100+1=101*/
  #id1 div{
  }
  /*权重为10+1=11*/
  .class1 div{
  }
  /*权重为10+10+1=21*/
  .class1 .class2 div{
  }

  如果权重相同，则最后定义的样式会起作用，但是应该避免这种情况出现
请解释一下为什么需要清除浮动？清除浮动的方式

清除浮动是为了清除使用浮动元素产生的影响。浮动的元素，高度会塌陷，而高度的塌陷使我们页面后面的布局不能正常显示。

  1、父级div定义height；
  2、父级div 也一起浮动；
  3、常规的使用一个class；
  	.clearfix:before, .clearfix:after {
  	    content: " ";
  	    display: table;
  	}
  	.clearfix:after {
  	    clear: both;
  	}
  	.clearfix {
  	    *zoom: 1;
  	}

  4、SASS编译的时候，浮动元素的父级div定义伪类:after
  	&:after,&:before{
  	    content: " ";
          visibility: hidden;
          display: block;
          height: 0;
          clear: both;
  	}

  解析原理：
  1) display:block 使生成的元素以块级元素显示,占满剩余空间;
  2) height:0 避免生成内容破坏原有布局的高度。
  3) visibility:hidden 使生成的内容不可见，并允许可能被生成内容盖住的内容可以进行点击和交互;
  4）通过 content:"."生成内容作为最后一个元素，至于content里面是点还是其他都是可以的，
  例如oocss里面就有经典的 content:".",有些版本可能content 里面内容为空,一丝冰凉是
  不推荐这样做的,firefox直到7.0 content:”" 仍然会产生额外的空隙；
  5）zoom：1 触发IE hasLayout。

  通过分析发现，除了clear：both用来闭合浮动的，其他代码无非都是为了隐藏掉content生成的内容，
  这也就是其他版本的闭合浮动为什么会有font-size：0，line-height：0。
什么是外边距合并？

  外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。
  合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。
  [w3school介绍网址：](http://www.w3school.com.cn/css/css_margin_collapsing.asp)
zoom:1的清除浮动原理?

  清除浮动，触发hasLayout；
  Zoom属性是IE浏览器的专有属性，它可以设置或检索对象的缩放比例。解决ie下比较奇葩的bug。
  譬如外边距（margin）的重叠，浮动清除，触发ie的haslayout属性等。

  来龙去脉大概如下：
  当设置了zoom的值之后，所设置的元素就会就会扩大或者缩小，高度宽度就会重新计算了，这里
  一旦改变zoom值时其实也会发生重新渲染，运用这个原理，也就解决了ie下子元素浮动时候父元素不随着自动扩大的问题。

  Zoom属是IE浏览器的专有属性，火狐和老版本的webkit核心的浏览器都不支持这个属性。然而，
  zoom现在已经被逐步标准化，出现在 CSS 3.0 规范草案中。

  目前非ie由于不支持这个属性，它们又是通过什么属性来实现元素的缩放呢？
  可以通过css3里面的动画属性scale进行缩放。
移动端的布局用过媒体查询吗？

假设你现在正用一台显示设备来阅读这篇文章，同时你也想把它投影到屏幕上，或者打印出来， 而显示设备、屏幕投影和打印等这些媒介都有自己的特点，CSS就是为文档提供在不同媒介上展示的适配方法

当媒体查询为真时，相关的样式表或样式规则会按照正常的级联规被应用。 当媒体查询返回假， 标签上带有媒体查询的样式表 仍将被下载 （只不过不会被应用）。

包含了一个媒体类型和至少一个使用 宽度、高度和颜色等媒体属性来限制样式表范围的表达式。 CSS3加入的媒体查询使得无需修改内容便可以使样式应用于某些特定的设备范围。

<style> @media (min-width: 700px) and (orientation: landscape){ .sidebar { display: none; } } </style>
使用 CSS 预处理器吗？喜欢那个？

  SASS (SASS、LESS没有本质区别，只因为团队前端都是用的SASS)
CSS优化、提高性能的方法有哪些？

  关键选择器（key selector）。选择器的最后面的部分为关键选择器（即用来匹配目标元素的部分）；
  如果规则拥有 ID 选择器作为其关键选择器，则不要为规则增加标签。过滤掉无关的规则（这样样式系统就不会浪费时间去匹配它们了);
  提取项目的通用公有样式，增强可复用性，按模块编写组件；增强项目的协同开发性、可维护性和可扩展性;
  使用预处理工具或构建工具（gulp对css进行语法检查、自动补前缀、打包压缩、自动优雅降级）；
浏览器是怎样解析CSS选择器的？

  样式系统从关键选择器开始匹配，然后左移查找规则选择器的祖先元素。
  只要选择器的子树一直在工作，样式系统就会持续左移，直到和规则匹配，或者是因为不匹配而放弃该规则。(从右往左匹配全部选择器)
在网页中的应该使用奇数还是偶数的字体？为什么呢？

偶数字号相对更容易和 web 设计的其他部分构成比例关系。
Windows 自带的点阵宋体（中易宋体）从 Vista 开始只提供 12、14、16 px 这三个大小的点阵，而 13、15、17 px 时用的是小一号的点阵（即每个字占的空间大了 1 px，但点阵没变），于是略显稀疏。
使用偶数是一种习惯的延续，并且12px和14px字体能形成更好的层次与对比。使用奇数号字体不好的地方是，文本段落无法对齐。
margin和padding分别适合什么场景使用？

  margin是用来隔开元素与元素的间距；padding是用来隔开元素与内容的间隔。
  margin用于布局分开元素使元素与元素互不相干；
  padding用于元素与内容之间的间隔，让内容（文字）与（包裹）元素之间有一段
抽离样式模块怎么写，说出思路，有无实践经验？[阿里航旅的面试题]

先通读视觉稿，把所有类似的、可复用的部分划分出来，抽出结构和样式做成模块。达到一段 HTML 代码、一段 CSS 样式，粘贴到任意位置都正常。

元素竖向的百分比设定是相对于容器的高度吗？

对于一些表示竖向距离的属性，例如padding-top,padding-bottom,margin-top,margin-bottom等，当按百分比设定它们时，依据的是父容器的宽度，而不是高度。

全屏滚动的原理是什么？用到了CSS的那些属性？

主要呈现方式有两种，一种是整体的元素一直排列下去，假设有五个需要展示的全屏页面，那么高度是500%，只是展示100%，剩下的可以通过tranform进行Y轴定位，也可以通过margin-top实现，第二种就是所有的子元素和页面一样，都显示在当前页面。

什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE？

面的设计和开发应当根据用户行为以及设备环境（系统平台、屏幕尺寸、屏幕定向等）进行相应的响应和调整.
响应式设计的基本原理是通过媒体查询检测不同的设备屏幕尺寸做处理。页面头部必须有meta声明viewport：
   <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no”>
兼容方案
1, 第一种：
2, 第二种：
3, 通过resize方法来实现PC端响应式
   $(window).resize(function () {
      screenRespond();
   });
视差滚动效果，如何给每页做不同的动画？（回到顶部，向下滑动要再次出现，和只出现一次分别怎么做？）

在web设计中，通过运用多层背景在以不同速度运动的情况下，形成的一种立体的运动效果，这种视觉体验，我们称之为视差效果。

* 1, 实现方式 css background-attachment: fixed;
* 2, 插件
* 3, [链接](http://www.alloyteam.com/2014/02/optimized-articles-of-parallax-scrolling-love-story/)
::before 和 :after中双冒号和单冒号 有什么区别？解释一下这2个伪元素的作用。

  单冒号(:)用于CSS3伪类，双冒号(::)用于CSS3伪元素。（伪元素由双冒号和伪元素名称组成）
  双冒号是在当前规范中引入的，用于区分伪类和伪元素。不过浏览器需要同时支持旧的已经存在的伪元素写法，
  比如:first-line、:first-letter、:before、:after等，
  而新的在CSS3中引入的伪元素则不允许再支持旧的单冒号的写法。

  想让插入的内容出现在其它内容前，使用::before，否者，使用::after；
  在代码顺序上，::after生成的内容也比::before生成的内容靠后。
  如果按堆栈视角，::after生成的内容会在::before生成的内容之上
如何修改chrome记住密码后自动填充表单的黄色背景 ？

  input:-webkit-autofill, textarea:-webkit-autofill, select:-webkit-autofill {
    background-color: rgb(250, 255, 189); /* #FAFFBD; */
    background-image: none;
    color: rgb(0, 0, 0);
  }
你对line-height是如何理解的？

line-height定义行高，设置行间的距离。应用方式是：用line-height减去font-size，得到的差（称为行间距）除2，分别添加到文本的顶部和底部。可以包含这些内容的最小框就是行框。

设置元素浮动后，该元素的display值是多少？

自动变成了 display:block 解决bug：（1）给浮动元素添加一个display：inline (2）给IE6写一个hack，其值为正常值的一半。

怎么让Chrome支持小于12px 的文字？

  1、用图片：如果是内容固定不变情况下，使用将小于12px文字内容切出做图片，这样不影响兼容也不影响美观。
  2、使用12px及12px以上字体大小：为了兼容各大主流浏览器，建议设计美工图时候设置大于或等于12px的字体大小，
  如果是接单的这个时候就需要给客户讲解小于12px浏览器不兼容等事宜。
  3、继续使用小于12px字体大小样式设置：如果不考虑chrome可以不用考虑兼容，同时在设置小于12px对象设置
  -webkit-text-size-adjust:none(PC上已失效)，做到最大兼容考虑。改为 transform:scale(0.875);
  [实现](https://www.zhihu.com/question/21093147?rf=21339583)
  4、使用12px以上字体：为了兼容、为了代码更简单 从新考虑权重下兼容性。
让页面里的字体变清晰，变细用CSS怎么做？

  -webkit-font-smoothing: antialiased;
font-style属性可以让它赋值为“oblique” oblique是什么意思？

  倾斜的字体样式（在css规范中这么描述的，让一种字体表示为斜体（oblique），如果没有这样样式，
  就可以使用 italic。oblique是一种倾斜的文字，不是斜体。）
position:fixed;在android下无效怎么处理？

  fixed的元素是相对整个页面固定位置的，你在屏幕上滑动只是在移动这个所谓的viewport，
  原来的网页还好好的在那，fixed的内容也没有变过位置，
  所以说并不是iOS不支持fixed，只是fixed的元素不是相对手机屏幕固定的。
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no"/>
如果需要手动写动画，你认为最小时间间隔是多久，为什么？（阿里）

  多数显示器默认频率是60Hz，即1秒刷新60次，所以理论上最小间隔为1/60＊1000ms ＝ 16.7ms
display:inline-block 什么时候会显示间隙？(携程)

  有空格的时候会有间隙（两个display:inline-block的默认的空格或者换行符），解决方法 移除空格、
  使用margin负值、使用font-size:0、letter-spacing、word-spacing
overflow: scroll时不能平滑滚动的问题怎么处理？

（1）-webkit-overflow-scrolling: touch;，是因为这行代码启用了硬件加速特性，所以滑动很流畅。 （2） isroll 方案

  overflow: auto 当页面出现滚动条时，会造成
  [跳动问题](http://www.zhangxinxu.com/wordpress/2015/01/css-page-scrollbar-toggle-center-no-jumping/)
（1）高度尺寸不确定的时候，使用：overflow-y：scroll;
（2）高度尺寸确定的，要么没有滚动条，要么直接出现，不会出现跳动。
（3） ```javascript .wrap-outer { margin-left: calc(100vw - 100%); } 或.wrap-outer { padding-left: calc(100vw - 100%); }

首先，.wrap-outer指的是居中定宽主体的父级，如果没有，创建一个（使用主体也是可以实现类似效果，不过本着宽度分离原则，不推荐）； 然后，calc是CSS3中的计算，IE10+浏览器支持，IE9浏览器基本支持(不能用在background-position上)； 最后，100vw相对于浏览器的window.innerWidth，是浏览器的内部宽度，注意，滚动条宽度也计算在内！而100%是可用宽度，是不含滚动条的宽度。 于是，calc(100vw - 100%)就是浏览器滚动条的宽度大小（如果有，如果没有滚动条则是0）！左右都有一个滚动条宽度（或都是0）被占用， 主体内容就可以永远居中浏览器啦，从而没有任何跳动！

有一个高度自适应的div，里面有两个div，一个高度100px，希望另一个填满剩下的高度。

*（1）height：calc（100%-100px） *（2）absolute positioning：外层position：relative；百分百自适应元素 position: absolute; top: 100px; bottom: 0; left: 0

flex 父元素display:flex; flex-direction: column; 下面的子元素的设置flex: 1;
png、jpg、gif 这些图片格式解释一下，分别什么时候用。有没有了解过webp？

1, png是便携式网络图片（Portable Network Graphics）是一种无损数据压缩位图文件格式， 优点是：压缩比高，色彩好。 大多数地方都可以用。
2, jpg是一种针对相片使用的一种失真压缩方法，是一种破坏性的压缩，在色调及颜色平滑变化做的 不错。 在www上，被用来储存和传输照片的格式。
3, gif是一种位图文件格式，以8位色重现真色彩的图像。可以实现动画效果时候
webp格式 是谷歌在2010年推出的图片格式，压缩率只有jpg的2/3，大小比png小了45%，缺点是压缩的时间更久了 。兼容性不好，目前谷歌和opera支持。

什么是Cookie 隔离？（或者说：请求资源的时候不要让它带cookie怎么做）

  如果静态文件都放在主域名下，那静态文件请求的时候都带有的cookie的数据提交给server的，非常浪费流量，
  所以不如隔离开。
静态资源放 CDN ，用 cookie free domain因为cookie有域的限制，因此不能跨域提交请求，故使用非 主要域名的时候，请求头中就不会带有cookie数据，这样可以降低请求头的大小，降低请求时间，从而达到 降低整体请求延时的目的。

  同时这种方式不会将cookie传入Web Server，也减少了Web Server对cookie的处理分析环节，
  提高了webserver的http请求的解析速度。
style标签写在body后与body前有什么区别？

　　* 1, 写在head标签中利于浏览器逐步渲染（resources downloading->CSSOM+DOM->RenderTree(composite)->Layout->paint）。 　　 CSS，解析CSS会产生CSS规则树。Javascript，脚本，主要是通过DOM API和CSSOM API来操作DOM Tree和CSS Rule Tree.

　　* 2, 写在body标签后由于浏览器以逐行方式对html文档进行解析，当解析到写在尾部的样式表（外联或写在style标签）会导致浏览 器停止之前的渲染，等待加载且解析样式表完成之后重新渲染，在windows的IE下可能会出现FOUC现象（即样式失效导致的页面闪烁问题）

基础知识——浏览器的渲染过程：(CSSOM视图模块(CSS Object Model View)

1, Create/Update DOM And request css/image/js：浏览器请求到HTML代码后，在生成DOM的最开始阶段（应该是 Bytes → characters 后），并行发起css、图片、js的请求，无论他们是否在HEAD里。注意：发起 js 文件的下载 request 并不需要 DOM 处理到那个 script 节点，比如：简单的正则匹配就能做到这一点，虽然实际上并不一定是通过正则：）。这是很多人在理解渲染机制的时候存在的误区。
2, Create/Update Render CSSOM：CSS文件下载完成，开始构建CSSOM
3, Create/Update Render Tree：所有CSS文件下载完成，CSSOM构建结束后，和 DOM 一起生成 Render Tree。
4, Layout：有了Render Tree，浏览器已经能知道网页中有哪些节点、各个节点的CSS定义以及他们的从属关系。下一步操作称之为Layout，顾名思义就是计算出每个节点在屏幕中的位置。
5, Painting：Layout后，浏览器已经知道了哪些节点要显示（which nodes are visible）、每个节点的CSS属性是什么（their computed styles）、每个节点在屏幕中的位置是哪里（geometry）。就进入了最后一步：Painting，按照算出来的规则，通过显卡，把内容画到屏幕上。
补充：

1, Repaint（重绘）：屏幕的一部分要重画。
2, Reflow（回流）：元件的几何尺寸变化了。要重新验证并计算Render Tree
3, 联想——<script>标签放到尾部是有必要的吗？
如果放到开始位置，假如js文件很大，解析到js文件所在的script标签的时候，js文件还没有下载完成，这时会阻塞并停止解析后面的HTML代码。当js文件下载完成并执行完之后才会继续后面的解析。所以是有必要的。

什么是CSS 预处理器 / 后处理器？

  - 预处理器例如：LESS、Sass、Stylus，用来预编译Sass或less，增强了css代码的复用性，
    还有层级、mixin、变量、循环、函数等，具有很方便的UI组件模块化开发能力，极大的提高工作效率。

  - 后处理器例如：PostCSS，通常被视为在完成的样式表中根据CSS规范处理CSS，让其更有效；目前最常做的
    是给CSS属性添加浏览器私有前缀，实现跨浏览器兼容性的问题。
