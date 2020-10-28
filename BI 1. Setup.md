# BI 1. Setup

## 0） Docker  

it's an OS like Terminal

​	安装好之后，重启，在powershell里用`docker info`查看是否成功安装。

​	报错：

​        WARNING: bridge-nf-call-iptables is disabled
​        WARNING: bridge-nf-call-ip6tables is disabled

​	解决：？？？相关方案都是linux上的。找不到解决方案。

​		似乎不太影响操作。先保留。
[link1](https://www.bilibili.com/video/av66604789?pop_share=1)
[link2](https://www.bilibili.com/video/BV1D5411j7Lb/)

用此命令从powershell访问docker

	docker exec -it bioinfo_tsinghua bash

用`exit`退回powershell

但是docker被设定为不手动终止就不会退出，手动终止的代码为：

	docker container stop 232e1bdfe7ee

改变docker的参数

​	can't find.

## 1) Vim

a kind of editor tool ,very professional.

>  It is hard to learn, but incredible to use.

[Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)

## 2) README 

**记录**好每个项目在做什么，记清每一步比冲冲冲更重要。

## 3） Backup your data

- How to ?

  - 1 Cloud storage

    - not for me

  - 2 System tools

    - complicate

  - **3 GitHub**

    - sounds famliar

    - according to **note BI-0** 

      


## Docker 安装到Linux上面

似乎需要。
安装代码存在印象笔记上
没有创建库，因为看不懂关于版本的那一部分代码，先往后跟。


​      

​      

​      