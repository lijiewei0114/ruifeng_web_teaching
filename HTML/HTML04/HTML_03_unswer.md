# HTML第三天作业 参考答案 

### 作业题目:

1.复习课上代码 回忆标签的使用

2.制作表格'英雄联盟英雄介绍',要求效果如下:



![qingyuanyuanxi](../../image/html/html03/lolhero.png)



完整效果图地址

[英雄联盟资料.pdf](../../file/html/html03/lolhero.pdf)

图片地址

[magestest.zip](../../file/html/html03/imagestest.zip)

3.制作注册页面,要求效果如下:

![qingyuanyuanxi](../../image/html/html03/hw02.png)

其中,'工作性质选择栏'默认选中会计,'健康状况'栏 字体均为绿色,'兴趣爱好'栏仅边框为红色

### 答案:

2.

	<!DOCTYPE html>
	<html>
		<head>
			<meta charset="UTF-8">
			<title></title>
		</head>
		<body>
			<div style="text-align: center;">
				<img src="../../img/hw180919/logo.jpg"/>
			</div>
			<p align="center"><a href="http://lol.qq.com/" style="font-size:30px ;" target="_blank"><img src="../../img/hw180919/logo.jpg"/></a></p>
			<table style="border: 1px solid;" rules="none" width="720px" align="center">
				
			<tr style="border: 1px solid;" align="center">
				<td width="200px" rowspan="2" style="border: 1px solid;">壁纸</td>
				<td width="20px" rowspan="2" style="border: 1px solid;">名称</td>
				<td width="50px" rowspan="2" style="border: 1px solid;">定位</td>
				<td width="90px" colspan="5" style="border: 1px solid;">技能</td>
	
			</tr>
			
			<tr style="border: 1px solid;" align="center">


				<td width="90px" style="border: 1px solid;">被动</td>
				<td width="90px" style="border: 1px solid;">Q</td>
				<td width="90px" style="border: 1px solid;">W</td>
				<td width="90px" style="border: 1px solid;">E</td>
				<td width="90px" style="border: 1px solid;">R</td>
			</tr>
			
			<tr style="border: 1px solid;" align="center">
				<td style="border: 1px solid;"><img src="../../img/hw180919/ali.jpeg" alt="九尾妖狐" width="200px"/></td>
				<td style="border: 1px solid;">九尾妖狐`阿狸</td>
				<td style="border: 1px solid;">法师.刺客</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/ali_skill_01.png"/><br />摄魂夺魄</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/ali_skill_02.png"/><br />欺诈宝珠</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/ali_skill_03.png"/><br />妖狐异火</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/ali_skill_04.png"/><br />魅惑妖术</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/ali_skill_05.png"/><br />灵魂突袭</td>
			</tr>
			
			<tr style="border: 1px solid;" align="center">
				<td style="border: 1px solid;"><img src="../../img/hw180919/timor.jpeg"/ alt="迅捷斥候" width="200px"/></td>
				<td style="border: 1px solid;">迅捷斥候`提莫</td>
				<td style="border: 1px solid;">射手.刺客</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/timor_skill_01.png"/><br />游击队军备</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/timor_skill_02.png"/><br />致盲吹箭</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/timor_skill_03.png"/><br />小莫快跑</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/timor_skill_04.png"/><br />毒性攻击</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/timor_skill_05.png"/><br />种蘑菇</td>
			</tr>
			
			<tr style="border: 1px solid;" align="center">
				<td style="border: 1px solid;"><img src="../../img/hw180919/Gold.jpeg"/ width="200px"></td>
				<td style="border: 1px solid;">暴走萝莉`金克斯</td>
				<td style="border: 1px solid;">射手</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/Gold_skill_01.png"/><br />罪恶快感</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/Gold_skill_02.png"/><br />枪炮交响曲</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/Gold_skill_03.png"/><br />震荡电磁波</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/Gold_skill_04.png"/><br />嚼火者手雷</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/Gold_skill_05.png"/><br />超究极死神飞弹</td>
			</tr>
			
			<tr style="border: 1px solid;" align="center">
				<td style="border: 1px solid;"><img src="../../img/hw180919/galen.png" width="200px"/></td>
				<td style="border: 1px solid;">德玛西亚之力`盖伦</td>
				<td style="border: 1px solid;">战士.坦克</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/galen_skill_01.png"/><br />坚韧</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/galen_skill_02.png"/><br />致命打击</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/galen_skill_03.png"/><br />勇气</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/galen_skill_04.png"/><br />审判</td>
				<td style="border: 1px solid;"><img src="../../img/hw180919/galen_skill_05.png"/><br />德玛西亚正义</td>
			</tr>
			<!--第七行-->
			<tr style="border: 1px solid;" align="center">
				<td colspan="8" style="border: 1px solid;">CopyRight © 1998 - 2017 TENCENT. ALL RIGHTS RESERVED.</td>
	
			</tr>
	
			</table>
		</body>
	</html>

3.

	<!DOCTYPE html>
	<html lang="zh">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<meta http-equiv="X-UA-Compatible" content="ie=edge" />
		<title>注册页面</title>
	</head>
	<body>
		<h1 align="center">注册界面</h1>
		<hr />
			<div align="center">	
				<form action="" method="post">	
					<p><label>账号:</label><input type="text" placeholder="请输入账号" required=""/></p>
					<p><label>密码:</label><input type="password" placeholder="请输入密码" required/></p>
					<p><label>性别:</label><input type="radio" name="sex" id="sex" checked/>保密
						<input type="radio" name="sex" id="sex"/>男
						<input type="radio" name="sex" id="sex"/>女
					</p>
					<p>
						<label>邮箱:</label><input type="text" placeholder="请输入邮箱"/>
					</p>
					<p>
						<label>电话:</label><input type="text" required="" placeholder="请输入电话"/>
					</p>
					<p>
						<select name="">
							<option value="">电子商务</option>
							<option value="">计算机</option>
							<option value="">会计</option>
						</select>
					</p>
					<p>
						<textarea name="" rows="15" cols="35" placeholder="请输入个性签名"></textarea>
					</p>
					<p>
						<fieldset style="width: 800px; color: green;">
							<legend align="center">健康信息</legend>
							<label for="">身高:</label><input type="text" />
							<label for="">体重:</label><input type="text" />
						</fieldset>
					</p>
					<p>
						<fieldset id="" style="border-color:red;">
							<legend align="center">兴趣爱好</legend>
							<input type="checkbox"/>抽烟
							<input type="checkbox"/>喝酒
							<input type="checkbox"/>烫头
							<input type="checkbox"/>洗脚
						</fieldset>
					</p>
					
					<input type="button" name="" id="" value="注册" />
					&nbsp;<input type="reset" name="" id="" value="重置" />
				</form>
			</div>
	</body>
	</html>



