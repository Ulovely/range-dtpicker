# range-dtpicker
uniapp组件：日期区间picker
### pdtPicker 日期区间选择器

可进行多粒度的时间选择器，组件名：``tranformText``，代码块： rangeDatePick。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import tfText from '@/components/tranformText/tranformText.vue';
export default {
    components: {tfText}
}
```

在 ``template`` 中使用组件

```html
<tfText txt='猪'></tfText>
或
<tfText :txt='txt'></tfText>
或
<tfText :txt='txt' :languageChange="type"></tfText> <!-- 如果需要当页切换语言，就用这个 -->
```

**tfText 属性说明：**

|属性名		|类型	|默认值	                    |说明					|
|---		|----	|---	                    |---					|
|txt		|String	|''	            			|中文文字	|
|languageChange	|String	|'zh-cn'				|改变文字语言类型|

**languageChange 值说明：**

|值 		|类型	|说明					|
|---		|----	|---					|
|'zh-cn'	|String	|简体中文			|
|'zh-tw'	|String	|繁体中文			|
|'en'		|String	|英语				|
|自定义语言类型	|String	|自定义语言类型	|


**更新记录：**

新增uniapp多语言组件

**感谢：**

> 有更多优化建议和需求，请联系作者。谢谢！
