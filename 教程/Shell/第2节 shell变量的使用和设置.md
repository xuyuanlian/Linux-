# 第2节 shell变量的使用和设置
```
#变量的使用和设置
变量

    脚本中自定义的变量 
    方便调用和修改 
	  常用驼峰命名法或小写字母命令自定义变量 
```
```
环境变量 
    系统定义的变量
    常用大写字母定义环境变量
    env命令查看系统的全局变量		
		
定义变量  
    name=value
    等号两边不能有空白字符，变量命名不要使用类似 name="zhang san"，调用时候容易产生歧义，需用下划线代替空白字符 name="zhang_san"
    命名只能使用英文字母，数字和下划线，首个字符不能以数字开头		
    中间不能有空格
    不能使用标点符号
    不能使用bash里的关键字
	
使用变量
    echo   "$name"
    printf "$name\n"
    调用变量容易产生歧义的时候，可使用${}区分
```
```
环境变量的设置
    便于理解
    变量配置在/etc/profile 那么所有用户在登陆的时候都会加载一次 
    变量配置在~/.bashrc    那么指定用户在登陆的时候都会加载一次
    配置中有export  则变量会传递给子shell,没有export则在当前shell可使用 
			
	
    当前终端设置的变量，终端关闭后变量设置就会失效
    添加永久环境变量 
        /etc/profile     全局变量设置,常见使用如JAVA_HOME,编辑完成使用source 命令重新加载
        JAVA_HOME=/usr/java/jdk1.8.0_60
        export PATH=$PATH:$JAVA_HOME/bin			
        export PATH=$PATH:/usr/local/software/mysql/bin
        ~/.bashrc        影响当前用户的变量,编辑完成使用source 命令重新加载
        设置别名  alias vi='vim'
				
    PATH变量
        echo $PATH	
        /root/.pyenv/shims:/root/.pyenv/bin:/root/perl5/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin 
        假如执行 ls命令，系统会在PATH中设置的路径去查找可执行命令		
```
```
常用shell内置变量 
    $0 $1 $2   传递参数的位置  $0表示脚本文件本身,$1是第1参数、$2是第2参数
    $#         传递参数的个数,不包括$0 
    $?         获取执行上一个指令的执行状态返回值（0为成功，非0为失败）
```