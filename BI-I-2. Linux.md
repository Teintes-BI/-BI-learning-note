# Linux

## Table of Contents 

- [基础命令](https://lulab2.gitbook.io/teaching/part-i.-basic-skills/2.linux/2.1.linux-basic-command)
  - 基本的一些东西
- [上机练习](https://lulab2.gitbook.io/teaching/part-i.-basic-skills/2.linux/2.2.linux-practice-guide)
  - 基因组注释文件 *.gtf `全称general feature format主要是用来对基因进行注释`,

![gtf每列的对应信息](D:\User\Documents\GitHub\-BI-learning-note\pic\gtf.png  "gtf每列的对应信息" )

	awk & sed
	类似于perl和python之类的简单语言，可以直接在命令行中使用，执行一些简单的（例如替换字符）操作。

wc 
- -l 统计文件行数
- -c 统计文件词数

grep 
- -v 排除以“？”开头的行
- -c 数有多少行
- -l 数有多少列
- - `^$` 代表空白
> grep -v -c pattern FILES  #(-v exclude -c count lines)
> grep -l pattern FILES #(-l: list of the files)

awk 语法
  因量大且复杂，另开一md
[awk-菜鸟教程](https://www.runoob.com/linux/linux-comm-awk.html)
	

	'{if($0!=" ") print}' 1.gtf | head -10  #过滤空行，显示前十行结果。

cut
- -f 1,2,3 #选取前三**列**
	如果数据量很大，记得加|head n=?
head,tail & cut 
	头，尾代表的是行，cut代表的是列
cat & paste 
	cat是行，paste是列

筛选特定的行
例 第三列为“gene”的行，且只显示1,3,9三列的数据
	cat 1.gtf | awk '$3 =="gene" { print $1, $3, $9 } ' |head
> head -100 FILE
> tail -100 FILE
> cut -f 2 FILE #(-f: field字段)
> cut -d ; -f 2 FILE #(-d change delimiter改分隔符)
> 
> cat FILES* > NEW_FILE
> paste FILES* > NEW_FILE

| 管道符
把前面部分得出来的结果进行重新处理，并且不显示前面那部分。

uniq
- - c count 计数，符合条件的行数有多少
- -d 打印出有重复出现的行，每种只打印一次
	当重复的行并不相邻时，uniq 命令是不起作用的，所以要用sort排序。

sort 按ASCII 排序并打印

![vim](D:/User/Documents/GitHub/-BI-learning-note/pic/vim.png)







- [Bash入门](https://lulab2.gitbook.io/teaching/part-i.-basic-skills/2.linux/2.3.linux-bash)

- sh文件必须要有声明语句,写在文件第一句。试了没写也能运行。
> #!/bin/bash

- 执行
	- sh + *.sh
	- ./*.sh (必须要有可执行权限)
		- chmod +x *.*
		- chmod +555 *.*

> if 条件1
> then 命令1
> elif 条件2
> then 命令2
> else 命令3
> fi
> 

![if判断参数](D:\User\Documents\GitHub\-BI-learning-note\pic\if判断参数.png)

- for

> for 变量名in列表
> do
> 命令1
> 命令2...
> done
> 

课程内容有问题。
主要去阅读鸟哥私房菜11-13chapter
另外看视频