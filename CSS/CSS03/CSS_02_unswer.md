# CSS第一天作业 参考答案 

### 作业题目:

1.复习课上代码 回忆div调整CSS样式 伪类选择器下拉菜单制作

2.制作一个网页下拉导航栏,效果要求如图所示:

![xialacaida](../../image/css/css02/css01.png)

其中,选择[用户]下拉出现墨绿色一栏,再次选择[博客]下拉出现黄色一栏,再次选择[我的博客],出现墨绿色一栏

3.制作一个注册界面,要求效果如图所示:

![xialacaida](../../image/css/css02/css02.png)

要求:使用一个四行三列的表格制作此表单  



### 答案:

2.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
    	.title{
            background-color: #2b99ff;
            height: 50px;
            line-height: 50px;
            text-align: center;
            color: #3d2fa2;
        }
        .user{
            width: 180px;
            height: 50px;
            margin-left: 20px;
            background-color: #7A7B50;
          

        }
        .dv1{
            display: none;
            width: 180px;
            height: 40px; 
            border: 1px solid red ;
            background-color: #787B53;
        }
        .dv20{
        	display: none;
        	margin: -50px 0 0 30px ;
        }
        .dv30{
        	display: none;
        	margin: -50px 0 0 200px;
        }
        .dv2{
           
            width: 200px;
            height: 40px; 
            border: 1px solid  ;
            background-color: lightgoldenrodyellow;
            margin: 0 0 0 150px;
            
        }
        .dv3{
            
            width: 200px;
            height: 40px; 
            border: 1px solid red ;
            background-color: #787B53;
        }
        .user:hover .dv1{
            display: block;
        }
        .dv11:hover .dv20{
        	display: block;
        }
        .dv23:hover .dv30{
        	display: block;
        }
    </style>
</head>
<body>
    <div class="title">
        <div class="user clearfix">用户
            <div class="dv1 dv11">
            	<a class="a1">博客
            		<div class="dv20">
	            		<div class="dv2">写博客</div>
	            		<div class="dv2">看博客</div>
	            		<div class="dv2 dv23">
	            			<a>我的博客
		            			<div class="dv30">
				            		<div class="dv3">全部博客</div>
				            		<div class="dv3">只看原创</div>
				            		<div class="dv3 dv33">只看转载</div>
			            		</div>
		            		</a>
	            		</div>
            		</div>
            	</a>
            </div>
            <div class="dv1"><a>闪存</a></div>
            <div class="dv1"><a>积分</a></div>
            <div class="dv1"><a>评论</a></div>
            <div class="dv1"><a>关注</a></div>
        </div>
        
    </div>
</body>
</html>
```

3.

```
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>表格+表单练习</title>
</head>
<body bgcolor="#F0F0F0">
    <form method="post">
        <table width="100%">
            <tr>
                <th colspan="2" ALIGN=CENTER><font size="5">注册新用户</font>
                </th>
            </tr>
            <tr>
                <td colspan="3"><hr>
                </td>
            </tr>
            <tr>
                <td width="400"></td>
                <td ALIGN=CENTER BGCOLOR="#ffffff">
                    <table width="400" cellpadding="4">
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">用户名</font></td>
                            <td ALIGN=LEFT><input tyoe="texe"></td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">登陆邮箱</font></td>
                            <td ALIGN=LEFT><input type="text"></td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">密码</font></td>
                            <td ALIGN=LEFT><input type="password"></td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">再输一次</font></td>
                            <td ALIGN=LEFT><input type="password"></td>
                        </tr>
                    </table></td>
                <td width="400"></td>
            </tr>
            <tr>
                <td width="400"></td>
                <td ALIGN=CENTER BGCOLOR="#ffffff">
                    <table width="400" cellpadding="4">
                        <tr>
                            <td colspan="2" ALIGN=CENTER><font size="3" face="微软雅黑">个人资料</font>
                            </td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">性别</font></td>
                            <td>男士<input type="radio" name="sex" value="man" checked>
                                女士<input type="radio" name="sex" value="woman">
                            </td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">学历</font></td>
                            <td>
                                <select name="city">
                                    <option value="benke">本科</option>
                                    <option value="dazhuani">大专</option>
                                    <option value="yanjiusheng">研究生</option>
                                    <option value="boshi">博士</option>
                                    <option value="zixue">自学</option>
                            </select>
                            </td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">职业</font></td>
                            <td>
                                <select name="occupation">
                                    <option value="student">在校学生</option>
                                    <option value="PHP">PHP工程师</option>
                                    <option value="Android">Android工程师</option>
                                    <option value="UI">UI设计师</option>
                                    <option value="IOS">IOS工程师</option>
                                    <option value="java">Java工程师</option>
                                    <option value="test">程序测试员</option>
                            </select>
                            </td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">所在城市</font></td>
                            <td>
                                <select name="city">
                                    <option value="beijing">帝都</option>
                                    <option value="shanghai">魔都</option>
                                    <option value="guangzhou">广州</option>
                                    <option value="hangzhou">杭州</option>
                                    <option value="tianjin">天津</option>
                                    <option value="haiwai">海外</option>
                            </select>
                            </td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">出生年月</font>
                            <td><select name="year">
                                    <option value="1985">1985</option>
                                    <option value="1986">1986</option>
                                    <option value="1987">1987</option>
                                    <option value="1988">1988</option>
                                    <option value="1989">1989</option>
                                    <option value="1990">1990</option>
                                    <option value="1991">1991</option>
                                    <option value="1992">1992</option>
                                    <option value="1993">1993</option>
                                    <option value="1994">1994</option>
                                    <option value="1995">1995</option>
                                    <option value="1996">1996</option>
                                    <option value="1997">1997</option>
                                    <option value="1998">1998</option>
                                    <option value="1999">1999</option>
                                    <option value="2000">2000</option>
                                    <option value="2001">2001</option>
                                    <option value="2002">2002</option>
                                    <option value="2003">2003</option>
                                    <option value="2004">2004</option>
                                    <option value="2005">2005</option>
                                    <option value="2006">2006</option>
                                    <option value="2007">2007</option>
                                    <option value="2008">2008</option>
                            </select> <select name="month">
                                    <option value="1">1月</option>
                                    <option value="2">2月</option>
                                    <option value="3">3月</option>
                                    <option value="4">4月</option>
                                    <option value="5">5月</option>
                                    <option value="6">6月</option>
                                    <option value="7">7月</option>
                                    <option value="8">8月</option>
                                    <option value="9">9月</option>
                                    <option value="10">10月</option>
                                    <option value="11">11月</option>
                                    <option value="12">12月</option>
                            </select></td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><font size="3" face="微软雅黑">猜你喜欢</font></td>
                            <td width="300"><input type="checkbox" name="hobby"
                                value="tiyu">体育 <input type="checkbox" name="hobby"
                                value="yinyue">音乐 <input type="checkbox" name="hobby"
                                value="youxi">游戏 <input type="checkbox" name="hobby"
                                value="bagua">八卦 <input type="checkbox" name="hobby"
                                value="tucao">吐槽</td>
                        </tr>
                        <tr>
                            <td ALIGN=RIGHT><input type="checkbox" name="accept"
                                value="accept">
                            </td>
                            <td><font size="3" face="微软雅黑">我已仔细阅读并接受&nbsp;&nbsp;<a
                                    href="Deom01.html">注册条款</a> </font>
                            </td>

                        </tr>
                        <tr>
                            <td ALIGN="center" colspan="3">
                            <input type="submit" value="注册">
                            <input type="reset" value="重置">
                        </tr>
                    </table></td>
                <td width="400"></td>
            </tr>
        </table>
    </form>
</body>
</html>
```

