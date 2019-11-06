### pdtPicker 日期区间选择器

可进行多粒度的时间选择器，组件名：``range-dtpicker``，代码块： rangeDatePick。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import rangeDatePick from '@/components/range-dtpicker/range-dtpicker.vue';
export default {
    components: {rangeDatePick}
}
```

在 ``template`` 中使用组件

```html
<rangeDatePick 
	:show="isShow"
	@showchange="showchange"
	start="1900-01"
	end="2200-12"
	:value="value"
	@change="bindChange"
	@cancel="bindCancel"
	themeColor="#4C83D6"
	fields="month"
></rangeDatePick>
```

**pdtPicker 属性说明：**

|属性名		|类型	|默认值	                    |说明					|
|---		|----	|---	                    |---					|
|themeColor	|String	|'#4C83D6'	            	|主题色	|
|start		|String	|'1900-01'					|限制选择器选择的最小时间	，粒度格式和value格式要相符，否则会又错误提示|
|end		|String	|'2200-12'					|限制选择器选择的最大时间	，粒度格式和value格式要相符，否则会又错误提示|
|value		|Array	|''	                        |当前日期选择器显示的时间	，粒度格式和value格式要相符，否则会又错误提示|
|fields		|String	|'month'	                |当前日期选择器粒度:year/month/day|


**value 值说明：**

|值 		|类型	|说明					|
|---		|----	|---					|
|[]			|Array	|当前日期选择器为开始时间的默认值			|
|['1900-01']	|Array	|当前日期选择器开始时间为1900-01			|
|['1900-01','2010-12']		|Array	|当前日期选择器开始时间为1900-01,结束时间为2010-12			|

**事件说明：**

|事件名称	|说明		|
|---|---|
|showchange	|必传，用于控制显示隐藏|
|change	|时间选择器点击【确定】按钮时时触发的事件，参数为选择器的当前的 value|
|cancel	|时间选择器点击【取消】按钮时时触发的事件|

**showchange事件说明：**

showchange(){
	this.isShow=!this.isShow;
}

**更新记录：**

1.0.1：新增组件——日期区间选择器
1.0.2：优化了开始日期和结束日期的切换，当前版本切换时会显示更合适的日期;添加了粒度选择，现支持year/month/day;
修复了demo的getDate -60年的获取问题
1.0.3：修复动态的value不能赋值问题；修复end值的可选值与实际填入的end值小一年问题

**感谢：**

> 有更多优化建议和需求，请联系作者。谢谢！
