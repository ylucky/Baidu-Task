## Baidu-Task ##
百度前端任务

查资料的过程中，看到了[百度前端技术学院][1]
的阶段任务，觉得十分不错，所以我决定把这个任务做下去。一方面检验自己，另一方面比对别人提交的代码，改正自己不足之处。
本代码仅供自己记录和学习。欢迎大家指出不足之处。

## 知识点 ##

```
1.border-collapse: collapse; 设置表格的边框被合并为一个单一的边框
2.overflow:auto;高度随着内容自动向下延伸
3.三栏布局，左右两边浮动，设置中间margin左右值即可。
4.border-radius: 0 0 50px 0;//  1/4圆
  border-radius可以同时设置1到4个值。
  如果设置1个值，表示4个圆角都使用这个值。
  如果设置两个值，表示左上角和右下角使用第一个值，右上角和左下角使用第二个值。
  如果设置三个值，表示左上角使用第一个值，右上角和左下角使用第二个值，右下角使用第三个值。
  如果设置四个值，则依次对应左上角、右上角、右下角、左下角（顺时针顺序）。
  border-radius[链接博客]（http://blog.sina.com.cn/s/blog_61671b520101gelr.html）
5.页面某一个版块固定，其他版块谁浏览器大小自适应，则浮动固定版块，自适应版块设置margin值古典版块即可，*千万不要写width*！
6.css
  a.text-decoration: underline;//下划线：
  b.text-transform：
		Capitalize 英文拼音的首字母大写
		Uppercase 英文拼音字母全大写
		Lowercase 英文拼音字母全小写
  c.透明度：
	opacity: 0.7;
	filter:alpha(opacity=70);/*IE*/
	-moz-opacity:0.7;/*ff*/
  d.字间距：
	word-spacing 属性增加或减少单词间的空白（即字间隔）。
	letter-spacing 属性增加或减少字符间的空白（字符间距）。
  e.斜体：
	font-style:normal;
	font-style:italic; /* 浏览器会显示一个斜体的字体样式。 */
	font-style:oblique;/*浏览器会显示一个倾斜的字体样式。 */
  f:c3选择器
	p:nth-child(2)   表示这个元素要是p标签，且是第二个子元素，是两个必须满足的条件。
	                 //first-child ,last-child
	p:nth-of-type(2) 表示父标签下的第二个p元素,不要在第二个位置。     
				     //first-of-type ,last-of-type
	p:not(:first-of-type)  选择器匹配非指定元素/选择器的每个元素。
  g:背景颜色透明
	filter: Alpha(Opacity=50);/* for IE */
    background-color: rgba(0, 0, 0, 0.5); /*for FF*/
  h:字体
	font:italic bold 12px/30px arial,sans-serif;
  i:背景图大小自适应
	background: url(../img/task7-banner.jpg) no-repeat;
	background-size:cover;
	-moz-background-size:cover;
	-webkit-background-size:cover;
  j:文本域禁止拖动大小
	resize: none;
  k:点击有蓝边
	a,input,button,select{
		border:0;outline:none;		
	}
  l:css3画三角形
	把元素的宽度、高度设为0。然后设置边框样式。
	http://www.jb51.net/article/42513.htm
  m:select去掉默认的小三角
	appearance:none;
	-moz-appearance:none; /* Firefox */
	-webkit-appearance:none; /* Safari 和 Chrome */
  n:设置一个元素为 box-sizing: border-box; 时，
  此元素的内边距和边框不再会增加它的宽度。
	* {
	 box-sizing:border-box;
	 -moz-box-sizing:border-box; /* Firefox */
	 -webkit-box-sizing:border-box; /* Safari */
	}
```


  [1]: http://ife.baidu.com/task/all
