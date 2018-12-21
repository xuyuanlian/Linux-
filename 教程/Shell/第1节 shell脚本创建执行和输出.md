# 第1节 shell脚本创建执行和输出
```
#shell脚本创建执行和输出
1.shell脚本开头 
  #!/bin/bash
	/bin/bash 是Bash的解释器命令的路径,定义解释该脚本所使用的解释器  
	#!/usr/bin/perl      perl脚本开头        解释型语言
	#!/usr/bin/python    python脚本开头      解释型语言
	#include <stdio.h>   C语言开头           编译型语言 


2.shell脚本的执行方式
    方式一 
	    sh  test.sh  |  bash  test.sh
            此种执行方式，没有使用#!/bin/bash 		
		
    方式二
	    脚本增加执行权限，将其转变为一个可执行的文件 
		    chmod  755  test.sh  | chmod +x test.sh 
		    ./test.sh  | /path/test.sh           相对路径和绝对路径的方式去执行脚本
              
3.终端中显示输出 
    echo   命令
    echo  "Hello World!"   双引号输出特殊字符需要使用转义符号"\" 
    echo  "Hello World\!"	
	echo  'Hello World!'   单引号会剥夺其中的所有字符的特殊含义
	echo  命令自动换行  ==》echo  -n  可以去除换行
	echo打印彩色输出
        显示：0(默认)、1(粗体/高亮)、22(非粗体)、4(单条下划线)、24(无下划线)、5(闪烁)、25(无闪烁)、7(反显、翻转前景色和背景色)、27(无反显)
		
        30      40      黑色
        31      41      红色
        32      42      绿色
        33      43      黄色
        34      44      蓝色
        35      45      紫红色
        36      46      青蓝色
        37      47      白色	
	    echo -e "\033[37;41m This is red text \033[0m"   红色打印
		echo -e "\033[37;41;5m This is red text \033[0m"

    echo -e 处理特殊字符
        若字符串中出现以下字符，则特别加以处理，而不会将它当成一般文字输出： 
        \a 发出警告声； 
        \b 删除前一个字符； 
        \c 最后不加上换行符号； 
        \f 换行但光标仍旧停留在原来的位置； 
        \n 换行且光标移至行首； 
        \r 光标移至行首，但不换行； 
        \t 插入tab； 		
        printf 命令 
        printf  "Hello\n"
        printf  "%-5s %-10s %-4s\n"   My Shopping list           #%-5s指明了一个格式为左对齐且宽度为5的字符串替换（-表示左对齐）
        printf  "%-5s %-10s %-4.2f\n" 1 apple     10             #%s 字符串类型  %f 浮点数  %d 整数
        printf  "%-5s %-10s %-4d\n"   2 tomato    20
        printf  "%-5s %-10s %-4.2f\n" 3 chicken   90
```