# HTML表格

## 表格描述

1. 表格由 table 标签来定义。
2. 每个表格均有若干行（由 tr 标签定义），每行被分割为若干单元格（由 td 标签定义）。
3. 字母 td(table data) 指表格数据，即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

#### 示例1

```
<table border="1">
    <tr>
        <td>
            row 1,col 1
        </td>
        <td>
            row 1,col 2
            
        </td>
    </tr>
    <tr>
        <td>
            row 2,col 1
        </td>
        <td>
            row 2,col 2
        </td>
    </tr>
</table>

```

#### 表格标签

| 标签       | 描述       |
| -------- | -------- |
| table    | 定义表格     |
| th       | 定义表格的表头  |
| tr       | 定义表格的行   |
| td       | 定义表格的单元  |
| caption  | 定义表格的标题  |
| colgroup | 定义表格的组   |
| col      | 定义表格列的属性 |
| thead    | 定义页眉     |
| tbody    | 定义表格的主体  |
| tfoot    | 定义表格的页脚  |

#### 表格边框属性

如果不定义边框属性，表格将不显示边框。有时这很有用，但是大多数时候，我们希望显示边框。

使用边框属性来显示一个带有边框的表格： border=“1” 线条宽为1 如果线条宽=0 则没有线条 有单元格边距为10

```
​```
		<table border=“1”   cellpadding="10”>
	单元格间距=0
		<table border="1" cellspacing="0”>
	单元格间距=10
		<table border="1" cellspacing="10”>
		
		
		<table cellpadding="10">
		    <tr>
		        <td>
		            row 1,col 1
		        </td>
		        <td>
		            row 1,col 2
		
		        </td>
		    </tr>
		    <tr>
		        <td>
		            row 2,col 1
		        </td>
		        <td>
		            row 2,col 2
		        </td>
		    </tr>
		</table>
​```

```

### 表格的三大部分

HTML中的table可以大致分为三个部分：

```
	thead ---------表格的页眉
	tbody ---------表格的主体
	tfoot ---------定义表格的页脚(在最下面,不管代码位置在哪里)

```

thead, tbody, tfoot 相当于三间房子，每间房子都可以用来放东西。

这个标签就是放在三间房子里面的东西，每一个 就是表格一行。

表格的每一行被分为一个个单元格。

每一个单元格就是用来存放数据的，这个数据分为两种：

1. 数据的名称；
2. 数据本身。

用 th标签 表示数据的名称(标题) ,

td标签表示真正的数据内容。

```
​```

		<table border="1">
	
	
	    <tfoot>
	    <tr><th>row end col1</th><th>row end col2</th></tr>
	    </tfoot>
	    <tbody>
	    <tr>
	        <td>
	            row 1,col 1
	        </td>
	        <td>
	            row 1,col 2
	
	        </td>
	    </tr>
	    <tr>
	        <td>
	            row 2,col 1
	        </td>
	        <td>
	            row 2,col 2
	        </td>
	    </tr>
	    </tbody>
	
	    <thead>
	    <tr><td>位置</td><td>位置</td></tr>
	    </thead>
	
	</table>
​```

```

#### 合并单元格

1. colspan 合并列

2. rowspan 合并行

   ```
   <table cellpadding="10" border="1">
       <tr>
           <td colspan="2">
               row 1,col 1
           </td>

           <td>
               row 1,col 2

           </td>
       </tr>
       <tr>
           <td>
               row 2,col 1
           </td>
           <td>
               row 2,col 2
           </td>
           <td rowspan="2">
               row 1,col 2

           </td>
       </tr>

       <tr>
           <td>
               row 2,col 1
           </td>
           <td>
               row 2,col 2
           </td>

       </tr>
   </table>

   ```

#### 对表格进行属性设置

<table style="border: 1px solid;" rules="none" width="720px" height="440px" align="center">

</table>

1.style标签

​	style标签风格设置,可以设置包括边框颜色等属性

2.width height

​	对表格的宽高进行设置(内部单元格不能超过表格总宽度)

3.align

​	左右对齐或居中

## 练习1

完成以下几个图片的练习

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/html/forms_and_tables/1.png)

## 练习2

完成以下几个图片的练习 ![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/html/forms_and_tables/2.png)

## 练习3

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/html/forms_and_tables/6.png)