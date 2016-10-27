## Baidu-Task ##
百度前端任务  

## 知识点 ##
js  

1.封装documnet  
```
var $=function(id){
	return document.getElementById(id);
}
```
2.input数值操作  
```
var handle=function(){
	var num=parseInt($("aqi-input").value);
	if(!isNaN(num)&&(num>0&&num<1000)){
		$("aqi-display").innerHTML=num;
	}else{
		alert($("aqi-input").value+"不是有效的AQI数值，请重新输入0-1000的有效整数！")
	}
}
```
3.键盘事件  
```
$("aqi-input").onkeyup=function(event){
	if(event.keyCode===13){
		handle();
	}
}
```
4.数组操作1-数组添加一维数组
```
var aqiData = [
  ["北京", 90],
  ["上海", 50],
  ["福州", 10],
  ["广州", 50],
  ["成都", 90],
  ["西安", 100]
];
var list=[];
for (var i = 0; i < aqiData.length; i++) {
	if(aqiData[i][1]>60){
		list.push(aqiData[i][0]+" "+aqiData[i][1]);
	}
}
```
4.1数组操作2-数组添加二维数组/数组嵌套
```
/*
data = [
["北京", 90],
["北京", 90]
……
]
*/
var data=[];
var li=document.getElementById("source").getElementsByTagName("li");
for (var i = 0; i < li.length; i++) {
	/*var cities=(li[i].innerHTML.substring(0,2));
	var num=(li[i].innerHTML.substring(10,12));*/

	var cities=(li[i].innerHTML.split("空气质量")[0]);
	var num=Number(li[i].children[0].innerHTML);
	data.push([cities,num]);
}
```
4.2对象操作  
```
/**
 * aqiData，存储用户输入的空气指数数据
 * 示例格式：
 * aqiData = {
 *    "北京": 90,
 *    "上海": 40
 * };
 */
var aqiData = {};
function addAqiData() {
	var city=$("aqi-city-input").value;
	var value=$("aqi-value-input").value;
	if (!city.match(/^[A-Za-z\u4E00-\u9FA5]+$/)) {
        alert("城市名必须为中英文字符！");
        return;
    }
    if (!value.match(/^\d+$/)) {
        alert("空气质量指数必须为整数！");
        return;
    }
	aqiData[city]=value;
	return aqiData;
}
```
5.创建新标签，添加内容  
```
for (var j = 0; j < list.length; j++) {
	var oli=document.createElement("li");
	oli.innerHTML="第"+arr[j]+"名"+list[j];
	oList.appendChild(oli);
}
```
6.从小到大排序
```
function sortAqiData(data) {
	data.sort(function(a,b){
		return a[1]-b[1]
	})
	return data;
}
```
7.添加数据1-ul>li  
```
function render(data) {
	var li = document.createElement("li");
	var resort = document.getElementById("resort");
	var items="";
	for (var i = 0; i < data.length; i++) {
		items+='第'+(i+1)+'名：'+data[i][0]+'空气质量：<b>'+data[i][1]+'</b><br/>';
	}
	resort.innerHTML=items;
}
```
8.添加数据2-表格  
```
function renderAqiList() {
	var items = "<tr><td>城市</td><td>空气质量</td><td>操作</td></tr>";
	for(var city in aqiData){
        items += "<tr><td>"+city+"</td><td>"+aqiData[city]+"</td><td><button data-city='"+city+"'>删除</button></td></tr>"
    }
	$("aqi-table").innerHTML=city?items:"";
}
```
9.删除对象属性
```
// 想办法给aqi-table中的所有删除按钮绑定事件，触发delBtnHandle函数
$("aqi-table").addEventListener("click", function(event){
    if(event.target.nodeName.toLowerCase() === 'button')
    	delBtnHandle.call(null, event.target.dataset.city);
})

/**
 * 点击各个删除按钮的时候的处理逻辑
 * 获取哪个城市数据被删，删除数据，更新表格显示
 */
function delBtnHandle(city) {
  // do sth.
  delete aqiData[city];
  renderAqiList();
}
```