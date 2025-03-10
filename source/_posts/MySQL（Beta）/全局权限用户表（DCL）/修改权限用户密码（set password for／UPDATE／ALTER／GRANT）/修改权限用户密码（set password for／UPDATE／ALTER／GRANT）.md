---
categories:
  - MySQL
tags:
  - DCL
date:
  - 2023-1-24 20:19:45
---

<body lang=zh-CN style='font-family:Calibri;font-size:11.0pt'>
<!--StartFragment-->

<div style='direction:ltr;border-width:100%'>

<div style='direction:ltr;margin-top:0in;margin-left:0in;width:8.8652in'>

<div style='direction:ltr;margin-top:0in;margin-left:0in;width:8.8652in'>

<ul type=disc style='direction:ltr;unicode-bidi:embed;margin-top:0in;
 margin-bottom:0in'>
 <li style='margin-top:0;margin-bottom:0;vertical-align:middle'><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt' lang=zh-CN>在</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt' lang=en-US>MySQL</span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt' lang=zh-CN>中，有四种方式可以修改权限用户的密码</span></li>
 <ul type=disc style='direction:ltr;unicode-bidi:embed;margin-top:0in;
  margin-bottom:0in'>
  <li style='margin-top:0;margin-bottom:0;vertical-align:middle'><span
      style='font-family:"Microsoft YaHei UI";font-size:12.0pt' lang=zh-CN>使用</span><span
      style='font-family:"Comic Sans MS";font-size:12.0pt' lang=en-US>set
      password for</span><span style='font-family:"Microsoft YaHei UI";
      font-size:12.0pt' lang=zh-CN>命令</span></li>
  <li style='margin-top:0;margin-bottom:0;vertical-align:middle'><span
      style='font-family:"Microsoft YaHei UI";font-size:12.0pt' lang=zh-CN>使用</span><span
      style='font-family:"Comic Sans MS";font-size:12.0pt' lang=en-US>UPDATA</span><span
      style='font-family:"Microsoft YaHei UI";font-size:12.0pt' lang=zh-CN>语句</span></li>
  <li style='margin-top:0;margin-bottom:0;vertical-align:middle'><span
      style='font-family:"Microsoft YaHei UI";font-size:12.0pt' lang=zh-CN>使用</span><span
      style='font-family:"Comic Sans MS";font-size:12.0pt' lang=en-US>ALTER</span><span
      style='font-family:"Microsoft YaHei UI";font-size:12.0pt' lang=zh-CN>语句</span></li>
  <li style='margin-top:0;margin-bottom:0;vertical-align:middle'><span
      style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>使用</span><span
      style='font-family:"Comic Sans MS";font-size:12.0pt'> GRANT </span><span
      style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>语句</span></li>
 </ul>
</ul>

<p style='font-family:"Comic Sans MS";font-size:12.0pt'>&nbsp;</p>

<p style='font-family:"Comic Sans MS";font-size:12.0pt'>&nbsp;</p>

<p style='font-size:13.5pt'><span style='font-weight:bold;
font-family:"Microsoft YaHei UI";color:#111111' lang=zh-CN>使用</span><span
style='font-weight:bold;font-family:"Comic Sans MS";color:#111111' lang=en-US>
set password for </span><span style='font-weight:bold;font-family:"Microsoft YaHei UI";
color:#111111' lang=zh-CN>命令</span><span style='font-family:"Microsoft YaHei UI"'
lang=zh-CN>&nbsp;</span></p>

<ul type=disc style='direction:ltr;unicode-bidi:embed;margin-top:0in;
 margin-bottom:0in'>
 <li style='margin-top:0;margin-bottom:0;vertical-align:middle'><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>在</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> MySQL </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>中，只有</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> root </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>用户可以通过更新</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> MySQL </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>数据库来更改密码。使用</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> root </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>用户登录到</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> MySQL </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>服务器后，可以使用</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> SET </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>语句来修改普通用户密码</span></li>
</ul>

<p style='font-family:"Microsoft YaHei UI";font-size:12.0pt'><span
style='font-weight:bold'>语法</span></p>

<p style='margin-left:.375in;font-size:12.0pt'><span
style='font-family:"Comic Sans MS"' lang=zh-CN>set password for </span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span><span
style='font-family:"Microsoft YaHei UI";color:#B43512' lang=zh-CN>用户名</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span><span
style='font-family:"Comic Sans MS"' lang=zh-CN>@</span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=en-US>'IP</span><span style='font-family:
"Microsoft YaHei UI";color:#B43512' lang=zh-CN>地址</span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=en-US>'</span><span style='font-family:
"Comic Sans MS"' lang=zh-CN> = password(</span><span style='font-family:"Comic Sans MS";
color:#B43512' lang=zh-CN>'</span><span style='font-family:"Microsoft YaHei UI";
color:#B43512' lang=zh-CN>新密码</span><span style='font-family:"Comic Sans MS";
color:#B43512' lang=zh-CN>'</span><span style='font-family:"Comic Sans MS"'
lang=zh-CN>)</span></p>

<p style='font-family:"Microsoft YaHei UI";font-size:12.0pt;
color:#70AD47'><span style='font-weight:bold'>示例</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>mysql&gt; SET PASSWORD FOR 'testuser'@'localhost' =
PASSWORD(&quot;newpwd&quot;);</p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>&nbsp;</p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>Query OK, 0 rows affected, 1 warning (0.01 sec)</p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>&nbsp;</p>

<p style='font-family:"Comic Sans MS";font-size:12.0pt'>&nbsp;</p>

<p style='font-family:"Comic Sans MS";font-size:12.0pt'>&nbsp;</p>

<p style='font-size:13.5pt;color:#111111'><span style='font-weight:
bold;font-family:"Microsoft YaHei UI"' lang=zh-CN>使用</span><span
style='font-weight:bold;font-family:"Comic Sans MS"' lang=en-US> </span><span
style='font-weight:bold;font-family:"Comic Sans MS"' lang=zh-CN>UPDATE</span><span
style='font-weight:bold;font-family:"Comic Sans MS"' lang=en-US> </span><span
style='font-weight:bold;font-family:"Microsoft YaHei UI"' lang=zh-CN>语法</span></p>

<p style='margin-left:.375in;font-size:12.0pt'><span
style='font-family:"Microsoft YaHei UI"' lang=zh-CN>&nbsp;使用</span><span
style='font-family:"Comic Sans MS"' lang=en-US>update</span><span
style='font-family:"Microsoft YaHei UI"' lang=zh-CN>语法修改直接</span><span
style='font-family:"Comic Sans MS"' lang=en-US>mysql.user</span><span
style='font-family:"Microsoft YaHei UI"' lang=zh-CN>中的密码字段</span></p>

<p style='font-family:"Microsoft YaHei UI";font-size:12.0pt'><span
style='font-weight:bold'>语法</span></p>

<p style='margin-left:.375in;font-family:"Microsoft YaHei UI";
font-size:12.0pt'>&nbsp;</p>

<p style='margin-left:.375in;font-size:12.0pt'><span
style='font-family:"Comic Sans MS";color:#2151FF' lang=en-US>UPDATE</span><span
style='font-family:"Comic Sans MS"' lang=en-US> user </span><span
style='font-family:"Comic Sans MS";color:#2151FF' lang=en-US>SET </span><span
style='font-family:"Comic Sans MS"' lang=zh-CN>authentication_string</span><span
style='font-family:"Comic Sans MS"' lang=en-US> = password(</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span><span
style='font-family:"Microsoft YaHei UI";color:#B43512' lang=zh-CN>新密码</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span><span
style='font-family:"Comic Sans MS"' lang=en-US>) </span><span style='font-family:
"Comic Sans MS";color:#2151FF' lang=en-US>WHERE</span><span style='font-family:
"Comic Sans MS"' lang=en-US> user = </span><span style='font-family:"Comic Sans MS";
color:#B43512' lang=en-US>'</span><span style='font-family:"Microsoft YaHei UI";
color:#B43512' lang=zh-CN>用户名</span><span style='font-family:"Comic Sans MS";
color:#B43512' lang=en-US>' </span><span style='font-family:"Comic Sans MS";
color:#2151FF' lang=en-US>AND</span><span style='font-family:"Comic Sans MS"'
lang=en-US> host = </span><span style='font-family:"Comic Sans MS";color:#B43512'
lang=en-US>'IP</span><span style='font-family:"Microsoft YaHei UI";color:#B43512'
lang=zh-CN>地址</span><span style='font-family:"Comic Sans MS";color:#B43512'
lang=en-US>'</span></p>

<p style='font-family:"Microsoft YaHei UI";font-size:12.0pt;
color:#70AD47'><span style='font-weight:bold'>示例</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'><span lang=zh-CN>mysql&gt;</span><span lang=en-US> USE mysql;</span></p>

<p style='margin-left:.375in;font-size:12.0pt'><span
style='font-family:"Comic Sans MS"' lang=zh-CN>mysql&gt; </span><span
style='font-family:"Comic Sans MS";color:#2151FF' lang=en-US>UPDATE</span><span
style='font-family:"Comic Sans MS"' lang=zh-CN> user </span><span
style='font-family:"Comic Sans MS";color:#2151FF' lang=en-US>SET</span><span
style='font-family:"Comic Sans MS"' lang=zh-CN> password</span><span
style='font-family:"Comic Sans MS"' lang=en-US> </span><span style='font-family:
"Comic Sans MS"' lang=zh-CN>=</span><span style='font-family:"Comic Sans MS"'
lang=en-US> </span><span style='font-family:"Comic Sans MS"' lang=zh-CN>password(</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=zh-CN>'123'</span><span
style='font-family:"Comic Sans MS"' lang=zh-CN>) </span><span style='font-family:
"Comic Sans MS";color:#2151FF' lang=en-US>WHERE</span><span style='font-family:
"Comic Sans MS"' lang=zh-CN> user</span><span style='font-family:"Comic Sans MS"'
lang=en-US> </span><span style='font-family:"Comic Sans MS"' lang=zh-CN>=</span><span
style='font-family:"Comic Sans MS"' lang=en-US> </span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=zh-CN>'root' </span><span style='font-family:
"Comic Sans MS";color:#2151FF' lang=en-US>AND </span><span style='font-family:
"Comic Sans MS"' lang=zh-CN>host</span><span style='font-family:"Comic Sans MS"'
lang=en-US> </span><span style='font-family:"Comic Sans MS"' lang=zh-CN>=</span><span
style='font-family:"Comic Sans MS"' lang=en-US> </span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=zh-CN>'localhost';</span><span
style='font-family:"Microsoft YaHei UI"' lang=zh-CN>&nbsp;</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'><span lang=zh-CN>Query OK, 0 rows affected</span><span lang=en-US>,1
warning</span><span lang=zh-CN> (0.</span><span lang=en-US>27</span><span
lang=zh-CN> sec)</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>&nbsp;</p>

<p style='margin-left:.375in;font-size:12.0pt'><span
style='font-family:"Comic Sans MS"'>mysql&gt; flush privileges;</span><span
style='font-family:"Microsoft YaHei UI"'>&nbsp;</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>Query OK, 0 rows affected (0.03 sec)</p>

<p style='margin-top:7pt;margin-bottom:7pt;font-family:"Comic Sans MS";
font-size:12.0pt'>&nbsp;</p>

<p style='margin-left:.375in;margin-top:7pt;margin-bottom:7pt;font-family:"Comic Sans MS";
font-size:12.0pt'>&nbsp;</p>

<p style='margin-top:7pt;margin-bottom:7pt;font-size:13.5pt'><span
style='font-weight:bold;font-family:"Microsoft YaHei UI"' lang=zh-CN>使用</span><span
style='font-weight:bold;font-family:"Comic Sans MS"' lang=en-US> ALTER </span><span
style='font-weight:bold;font-family:"Microsoft YaHei UI"' lang=zh-CN>语法</span></p>

<ul type=disc style='direction:ltr;unicode-bidi:embed;margin-top:0in;
 margin-bottom:0in'>
 <li style='margin-top:0;margin-bottom:0;vertical-align:middle;margin-top:7pt;
     margin-bottom:7pt'><span style='font-family:"Microsoft YaHei UI";
     font-size:12.0pt' lang=zh-CN>使用</span><span style='font-family:"Comic Sans MS";
     font-size:12.0pt' lang=en-US>ALTER</span><span style='font-family:"Microsoft YaHei UI";
     font-size:12.0pt' lang=zh-CN>对数据表中的密码字段进行修改</span></li>
</ul>

<p style='margin-top:7pt;margin-bottom:7pt;font-family:"Microsoft YaHei UI";
font-size:12.0pt'><span style='font-weight:bold'>语法</span></p>

<p style='margin-left:.375in;margin-top:7pt;margin-bottom:7pt;font-size:12.0pt'><span
style='font-family:"Comic Sans MS";color:#2151FF' lang=en-US>ALTER</span><span
style='font-family:"Comic Sans MS"' lang=en-US> USER </span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span><span
style='font-family:"Microsoft YaHei UI";color:#B43512' lang=zh-CN>用户名</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span><span
style='font-family:"Comic Sans MS"' lang=en-US>@</span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=en-US>'IP</span><span style='font-family:
"Microsoft YaHei UI";color:#B43512' lang=zh-CN>地址</span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=en-US>' </span><span style='font-family:
"Comic Sans MS";color:#2151FF' lang=en-US>IDENTIFIED WITH</span><span
style='font-family:"Comic Sans MS"' lang=en-US> mysql_native_password </span><span
style='font-family:"Comic Sans MS";color:#2151FF' lang=en-US>BY </span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span><span
style='font-family:"Microsoft YaHei UI";color:#B43512' lang=zh-CN>密码</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=en-US>'</span></p>

<p style='margin-top:7pt;margin-bottom:7pt;font-family:"Microsoft YaHei UI";
font-size:12.0pt;color:#70AD47'><span style='font-weight:bold'>示例</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'><span lang=zh-CN>mysql&gt; </span><span style='color:#2151FF'
lang=en-US>ALTER</span><span lang=en-US> USER 'root'@'localhost' </span><span
style='color:#2151FF' lang=en-US>IDENTIFIED WITH</span><span lang=en-US>
mysql_native_password </span><span style='color:#2151FF' lang=en-US>BY</span><span
lang=en-US> '123456';</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'><span lang=zh-CN>Query OK, 0 rows affected</span><span lang=en-US>,1
warning</span><span lang=zh-CN> (0.</span><span lang=en-US>27</span><span
lang=zh-CN> sec)</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>&nbsp;</p>

<p style='margin-left:.375in;font-size:12.0pt'><span
style='font-family:"Comic Sans MS"'>mysql&gt; flush privileges;</span><span
style='font-family:"Microsoft YaHei UI"'>&nbsp;</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt'>Query OK, 0 rows affected (0.03 sec)</p>

<p style='font-family:"Comic Sans MS";font-size:12.0pt'>&nbsp;</p>

<p style='font-family:"Comic Sans MS";font-size:12.0pt'>&nbsp;</p>

<p style='font-family:"Comic Sans MS";font-size:12.0pt'>&nbsp;</p>

<p style='font-size:13.5pt'><span style='font-weight:bold;
font-family:"Microsoft YaHei UI"'>使用</span><span style='font-weight:bold;
font-family:"Comic Sans MS"'> GRANT </span><span style='font-weight:bold;
font-family:"Microsoft YaHei UI"'>语句</span></p>

<ul type=disc style='direction:ltr;unicode-bidi:embed;margin-top:0in;
 margin-bottom:0in'>
 <li style='margin-top:0;margin-bottom:0;vertical-align:middle'><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>还可以在全局级别使用</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> GRANT USAGE </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>语句指定某个账户的密码而不影响账户当前的权限。需要注意的是，使用</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> GRANT </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>语句修改密码，必须拥有</span><span
     style='font-family:"Comic Sans MS";font-size:12.0pt'> GRANT </span><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>权限。一般情况下最好使用该方法来指定或修改密码</span></li>
</ul>

<p style='font-family:"Microsoft YaHei UI";font-size:12.0pt'><span
style='font-weight:bold'>语法</span></p>

<p style='margin-left:.375in;font-size:12.0pt'><span
style='font-family:"Comic Sans MS"' lang=zh-CN>GRANT USAGE ON *.* TO </span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=zh-CN>'</span><span
style='font-family:"Microsoft YaHei UI";color:#B43512' lang=zh-CN>用户名</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=zh-CN>'</span><span
style='font-family:"Comic Sans MS"' lang=zh-CN>@</span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=zh-CN>’</span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=en-US>IP</span><span style='font-family:
"Microsoft YaHei UI";color:#B43512' lang=zh-CN>地址</span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=zh-CN>’</span><span style='font-family:
"Comic Sans MS"' lang=zh-CN> IDENTIFIED BY </span><span style='font-family:
"Comic Sans MS";color:#B43512' lang=zh-CN>'</span><span style='font-family:
"Microsoft YaHei UI";color:#B43512' lang=zh-CN>新密码</span><span
style='font-family:"Comic Sans MS";color:#B43512' lang=zh-CN>'</span></p>

<p style='font-family:"Microsoft YaHei UI";font-size:12.0pt;
color:#70AD47'><span style='font-weight:bold'>示例</span></p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt;color:black'>mysql&gt; GRANT USAGE ON *.* TO 'testuser'@'localhost'
IDENTIFIED BY 'newpwd3';</p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt;color:black'>&nbsp;</p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt;color:black'>Query OK, 0 rows affected, 1 warning (0.05 sec)</p>

<p style='margin-left:.375in;font-family:"Comic Sans MS";font-size:
12.0pt;color:black'>&nbsp;</p>

<ul type=disc style='direction:ltr;unicode-bidi:embed;margin-top:0in;
 margin-bottom:0in'>
 <li style='margin-top:0;margin-bottom:0;vertical-align:middle;color:black'><span
     style='font-family:"Microsoft YaHei UI";font-size:12.0pt'>由运行结果可以看出，密码修改成功。</span></li>
</ul>

</div>

</div>

</div>

<!--EndFragment-->
</body>
