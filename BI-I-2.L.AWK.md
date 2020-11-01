# AWK 语法

- 只能用单引号 ‘{}’直接使用print，用$+数字定义列数

- 默认的列与列之间的区分标准（分割字符）是空格或tab
    - 自定义分割字符的方式：
    - -F `awk -F, '{print $1,$2}'   log.txt`
    - 使用多个分隔符.先使用空格分割，然后对分割结果再使用","分割
    - `$ awk -F '[ ,]'  '{print $1,$2,$5}'   log.txt`
- 设置变量
   - awk -v

    - ` $ awk -va=1 '{print $1,$1+a}' log.txt`

    - `$ awk -va=1 -vb=s '{print $1,$1+a,$1b}' log.txt`

    - 变量为数字时，和字母相加，变为数字？？？

    - 变量为字母是，和数字相加，就跟到了数字后面
     > 变量：分为内置变量和自定义变量;输入分隔符FS和输出分隔符OFS都属于内置变量。内置变量就是awk预定义好的、内置在awk内部的变量，而自定义变量就是用户定义的变量。

> ```
>       >  $ awk -va=1 '{print $1,$1+a}' log.txt
>       >  ---------------------------------------------
>       >  2 3
>       >  3 4
>       >  This's 1
>       >  10 11
>       >  $ awk -va=1 -vb=s '{print $1,$1+a,$1b}' log.txt
>       >  ---------------------------------------------
>       >  2 3 2s
>       >  3 4 3s
>       >  This's 1 This'ss
>       >  10 11 10s
>       > ```
> ```

![运算符](D:\User\Documents\GitHub\-BI-learning-note\pic\AWK运算符.png)

![内建变量](D:\User\Documents\GitHub\-BI-learning-note\pic\AWK变量.png)

- split 用法
	- wk的内建函数split允许你把一个字符串分隔为单词并存储在数组中。你可以自己定义域分隔符或者使用现在FS(域分隔符)的值。
格式：

     split (string, array, field separator)
     split (string, array)  -->如果第三个参数没有提供，awk就默认使用当前FS值

- gsub用法
	- gsub("要被替换的", "替换成什么", 替换哪里的)
  `除了正则表达式所有具体值被替代这点，它和 sub 函数完全一样地执行。`???

