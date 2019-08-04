---
layout: post
title:  "PowerDesigner导出SQL时如何添加注释"
date:   2019-03-18 07:10:27
categories: 张明远
---
使用PowerDesigner编写数据库模型需要重复添加备注，导致很不方便，下面介绍两种添加注释的方法：

方法一

1.第一步，打开实体表，选择“Column”tab，双击每一个column（也可以右键点击，然后在悬浮窗中点击“Properties”），如下图所示：

<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img1.png" />

2.第二步，在“Comment”中输入注释信息，点击“确定”，如下图所示：

<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img3.png" />

3.第三步，选择“Preview”tab，查看SQL预览，发现我们编辑的column已经有了注释信息，如下图所示：

<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img3.png" />

但是该注释方法同已经定义过的Name重复，导致重复工作，可不可以指定一次，完成Name和注释同事添加呢？请往下看

方法二

1.第一步，按“Database”>>“Edit Current DBMS..”打开，如下图所示：

<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img4.png" />

2.第一步，按“Script”>>“Object”>>“Column”>>“ColumnComment”打开，然后将value中的信息改成“alter table [%QUALIFIER%]%TABLE% modify column %COLUMN% %DATATYPE% comment %.60qA:COMMENT%”，最后点击“确定”（注意：不包含双引号，否则导入mysql语法报错）如下图所示：

<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img5.png" />

3.第三步，如果有提示弹框，则选择“是”，如下图所示：
<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img6.png" />

4.第四步，打开实体表，选择“Preview”tab，点击图中的图标按钮，如下图所示：
<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img7.png" />

5.第五步，勾选图中的选项，这里设置会当comment为空时，自动将name作为comment，然后点击“确定”
<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img8.png" />

6.第六步，查看SQL预览，发现对所有的column添加了注释，如下图所示：
<img class="" src="/images/blog/2019-03-18-PowerDesigner导出SQL时如何添加注释/img9.png" />

[张明远]:      https://zmy1123347389.github.io/
