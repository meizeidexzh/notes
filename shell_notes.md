## shell中的变量
> shell中的变量分为全局变量（环境变量）和局部变量（本地变量）

可以用`env`或者`set`来查看全部的环境变量

**环境变量**
> 环境变量是一种特殊的变量，任何shell都可以直接包含或者调用的变量 例如

```
PATH: 指定可执行程序的搜索路径，这个变量包含很多路径，用冒号分隔
LID_LIBRARY_PATH: 指定动态库的搜索路径
```



环境变量又氛围**系统环境变量**和**自定义环境变量**

**环境变量的操作**
```
echo $env_var
export //设置一个新的环境变量
env //显示所有的环境变量，名称及其值
set //显示本地定义的shell变量
unset //清除环境变量
readonly //设置只读环境变量

```


**环境表**
> 所有的环境变量在程序中通过环境表获取； 环境表是一个全局变量，类型为字符串数组指针（二级指针）， 以NULL结束


## 作业控制

**查看jobs**
- `jobs` 
- `jobs -l` 显示pid

**以后台方式运行程序**
- `cmd &`在后台运行指令cmd

**将后台程序放到前台**
- `fg %num` 将job号为num的任务放到前台

**将正在运行的任务放到后台**
- 首先 `Ctrl + z` 暂停任务
- `bg`将前台任务转到后台
- `bg`后暂停的程序又恢复运行了

**恢复stoped状态的任务**
- 方法1：`kill -stop | -19 | -sigstop | SIGSTOP | STOP %num`
- 方法2：`bg`(只有一个任务) 或者 `bg %num`(多个任务)
- 方法3：`fg` 或者 `fg %num`

**前台进程的终止**
- `Ctrl + c` 或者 `Ctrl + \`

**后台进程的终止**
- 方法1：通过`jobs`查看job号，然后`kill %num`
- 方法2：通过`jobs -l`查看pid，然后`kill -9 pid`







## shell语法规则


- **变量赋值` = `号前后不能有空格**
```
//正确的
a=10
b=20

//错误的
a = 10
b = 10

```

#### shell中的括号
**单圆括号**


**双圆括号**
```


```


**if 判断语句**

- `[`的后面必须要有空格，`]`的前面也是必须要有空格；
- 里面的表达式`$a != $b` 或者 `$a!=$b`都是可以的


**将`if-then-fi`语句写成一行**
```bash
if [ $a -gt $b]; then echo "hahaha"; fi;
if ((i > 5)); then echo "wo wu di le"; fi;
```

**将for语句写成一行**
```bash

for i in $(seq 0 4);do echo $i;done  
for i in `seq 0 4`;do echo $i;done  
for ((i=0;i<5;i++));do echo $i;done  
for i in {0..4};do echo $i;done
```

**数值运算后赋值的方法**
```bash
a=10 b=20;
c=$[a+b] //表达式a+b的前后与括号之间不能有空格的
c=$[a + b] //+号前后都是可以有空格的

c=`expr a + b` //反引号不是单引号
//+号运算符的前后要有空格
//=号的前后不能有空格
//expr的前后不能有空格


```

**shell中的字符串**
```bash
//不含转义字符和空格的时候，加不加引号都无所谓
a=abc b="abc" //a和b是相等的

//如果字符串中含有空格什么的就需要加引号
a="abc d" //可以赋值
b=abc d //无法完成赋值

//单引号内不能出现单引号
//双引号里面可以出现双引号


```

**遍历命令行运行的结果**
```bash
for file in `ls`; do echo $file; echo -e "\n"; done;

```

## 文本处理

#### grep基础教程

