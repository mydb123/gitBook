---
title: html标签
---
## 标签
+ `<p></p>`段落标签  

+ `<br/>`换行标签   
+ `<strong></strong>`或者`<b></b>` 加粗
+ `<em></em>`或者`<i></i>`倾斜
+ `<del></del>`或者`<s></s>`删除
+ `<ins></ins>`或者`<u></u>`下划线
+ `&nbsp`空格
+ `table`表格
```html
        <taber>
            <!-- 行 -->
            <tr>
                <!-- 表头单元格 -->
                <th></th>
                <td></td>
                <!-- 单元格 -->
                <td></td>
                <td></td>
            </tr>
    </taber>
```
+  无序列表
```html
    <ul>
       <li></li>
       <li></li>
       <li></li>
   </ul>
```
+ 自定义列表(网页最下端)
```html
    <dl>
       <dt></dt>
       <dd></dd>
       <dd></dd>
    </dl>
```
## 表单
+  `<from></from>`这就是表单域(用于登录和一些文档处)    

+ `<input type="下面以列出常用可选值"></input>` 输入框
    > text (文本框) 
    > password (密码框) 
    > radio (单选) 
    > checkbox (多选) 
+ 下拉菜单  
```html
<select>
    <option></option>
    <option></option>
    <option></option>
    <option selected="selected">默认选中</option>
</select>
```

+ `<textarea rows="每行字数" cols="多少行">内容</textarea>` 多行文本


## 快速生成html结构
1.  **生成多个div标签:** `div*10`    

2. **如何形成父子级关系:** `ul>li`  

3. **如何形成兄弟级关系:** `ul+li`  

4. **直接生成class类名:** `.nav` 

5. **直接生成带需要指定标签class类名:** `span.nav` 

6. **生成div类名是有顺序的:** `.nav$5`   吧   

## 行内元素和块级元素
1. **行内元素列表:**
```md
<a>标签可定义锚
<b></b>字体加粗
<br>换行
<em>定义为强调的内容
<i>斜体文本效果
<img>图像
<label>标签
<input>输入框
<select>多选菜单
<span>行内元素
<strong>语气更强的强调的内容
<textarea>多行的文本输入控件

```


2. **块级元素列表:**
```md
<dd>定义列表中定义条目
<div>定义文档中的分区或节
<dl>定义列表
<dt>定义列表中的项目
<form>创建 HTML 表单
<h1>定义最大的标题
<hr>创建一条水平线
<li>标签定义列表项目
<ol>定义有序列表
<ul>定义无序列表
<p>标签定义段落
<table>标签定义 HTML 表格
<tbody>标签表格主体（正文）
<td>表格中的标准单元格
<th>定义表头单元格
<tr>定义表格中的行
```