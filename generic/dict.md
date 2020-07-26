数据字典。

**使用方式**

根据数据字典的type和value显示label：

标签的方式：
```html
<dict:value type="locale" value="en_US"/>
```

属性的方式：
```html
<div dict:value="en_US" type="locale"></div>
```




数据字典列表

1、dict:value

用法示例：

    <dict:value id="id1" name="id1" type="sex" value="1"/>
    
或  

    <div dict:value="sex" id="id2" name="id2" value="2"></div>
    
参数说明：

    type:数据字典类型 在dict:value为属性的情况下，dict:value="sex"中的值就是type
    
    value：数据字典的值
    
    id:元素的id
    
    name：元素的name
    
    class：元素的class样式 
    
    style: 元素的style样式
    
    
2、dict:select

    适用于大于等于2个数据字典项的用于select元素显示

用法示例：

    <dict:select id="id5" name="id5" type="sex" isIncludeAll="true" selected="1"/>
    
或  

    <div dict:select="sex" id="id6" name="id6" selected="2"></div>
    
参数说明：

    type:数据字典类型 在dict:select为属性的情况下，dict:select="sex"中的值就是type
    
    id:元素的id
    
    name：元素的name
    
    selected: 选中的值
    
    isIncludeAll: 选项值中是否包含”所有“选项（值为”“）
    
    class：元素的class样式 
    
    style: 元素的style样式
    
    
3、dict:checkbox

    适用于等于2个数据字典项的用于checkbox元素显示

用法示例：

    <dict:checkbox id="id3" name="id3" type="sex" isChecked="false"/>
 
或  

    <div dict:checkbox="sex" id="id4" name="id4" isChecked="true"></div>
    
参数说明：

    type:数据字典类型 在dict:checkbox为属性的情况下，dict:checkbox="sex"中的值就是type
    
    id:元素的id
    
    name：元素的name
    
    isChecked: 选中的值
    
    class：元素的class样式 
    
    style: 元素的style样式    


4、dict:checkboxScript

    用于在页面上打印javascript的模板，适用于等于2个数据字典项的用于checkbox元素显示

用法示例：

    <dict:checkboxScript scriptId="abcScript" checkBoxId="abc" checkBoxName="abc" type="sex" valueField="id" checkedField="status" checkedValue="1"/>
    
    页面结果：
    
    ```html
    <!--表格的abc列-->
    <script type='text/html' id='abcScript' >
        <input type='checkbox' id='abc' lay-filter='abc'  name='abc' value="{{d.id}}" lay-text='男|女' {{d.status==1?'checked':''}} lay-skin='switch' class='' style='' ></input>
    </script>
    ```
 
或  

    <div dict:checkboxScript="sex" scriptId="testScript" checkBoxId="test" checkBoxName="test" valueField="id" checkedField="status" checkedValue="1"/>
    
    页面结果：
    
    ```html
        <!--表格的test列-->
        <script type='text/html' id='testScript' >
            <input type='checkbox' id='test' lay-filter='test'  name='test' value="{{d.id}}" lay-text='男|女' {{d.status==1?'checked':''}} lay-skin='switch' class='' style='' ></input>
        </script>
    ```
    
参数说明：

    type:数据字典类型 在dict:checkbox为属性的情况下，dict:checkbox="sex"中的值就是type
    
    id:元素的id
    
    name：元素的name
    
    isChecked: 选中的值
    
    class：元素的class样式 
    
    style: 元素的style样式   
