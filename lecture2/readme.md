# [Shell Tools and Scripting](https://missing.csail.mit.edu/2020/shell-tools/)

### 习题

<details>
    <summary>write an ls command that lists files in the following manner</summary>



### 题目详情

Read [`man ls`](http://man7.org/linux/man-pages/man1/ls.1.html) and write an `ls` command that lists files in the following manner

- Includes all files, including hidden files
- Sizes are listed in human readable format (e.g. 454M instead of 454279954)
- Files are ordered by recency
- Output is colorized

A sample output would look like this

```bash
-rw-r--r--   1 user group 1.1M Jan 14 09:53 baz
 drwxr-xr-x   5 user group  160 Jan 14 09:53 .
 -rw-r--r--   1 user group  514 Jan 14 06:42 bar
 -rw-r--r--   1 user group 106M Jan 13 12:12 foo
 drwx------+ 47 user group 1.5K Jan 12 18:08 ..
```

### 翻译

阅读 man ls 并且让ls命令按照如下条件输出

+ 包括所有文件，包括隐藏文件
+ 文件大小转换成好理解的格式 比如 454M 而不是 454279954
+ 文件按照最近修改的日期排序
+ 输出有颜色

下面是示例

```bash
-rw-r--r--   1 user group 1.1M Jan 14 09:53 baz
 drwxr-xr-x   5 user group  160 Jan 14 09:53 .
 -rw-r--r--   1 user group  514 Jan 14 06:42 bar
 -rw-r--r--   1 user group 106M Jan 13 12:12 foo
 drwx------+ 47 user group 1.5K Jan 12 18:08 ..
```

### 解答

+ 显示所有文件

```bash
~ » ls -a  
```

+ 文件大小格式

```bash
~ » ls -lh                                                                                                                                                                   130 ↵ sky@sky-virtual-machine
total 52K
drwxr-xr-x 11 sky sky 4.0K 5月  24 08:35 Desktop
drwxr-xr-x  2 sky sky 4.0K 5月  13 23:04 Documents

```
+ 文件顺序

```bash
~ » ls -lt                                                                                                                                                                         sky@sky-virtual-machine
total 52
drwxr-xr-x 11 sky sky 4096 5月  24 08:35 Desktop
-rw-rw-r--  1 sky sky    6 5月  22 14:00 hello.txt
drwxr-xr-x  5 sky sky 4096 5月  20 10:31 Downloads

```

+ 输出有颜色

```bash
# 我这个本身就有颜色的
```

</details>

<details>
    <summary>write bash functions marco and polo that do the following</summary>


### 题目详情

write bash functions  `marco` and `polo` that do the following. Whenever you execute `marco` the current working directory should be saved in some manner, then when you execute `polo`, no matter what directory you are in, `polo` should `cd` you back to the directory where you executed `marco`. For ease of debugging you can write the code in a file `marco.sh` and (re)load the definitions to your shell by executing `source marco.sh`.

### 翻译

写两个bash函数功能如下。当你运行marco，当前的工作目录会用某种方式保存，之后当你运行polo的时候，不论你当前在哪个目录，polo会cd回到运行marco的目录。为了方便debug你可以将代码写进marco.sh并且通过source marco.sh加载这个命令.

### 解答
marco脚本中要保留pwd命令的值
polo脚本要cd到marco脚本保留到的变量中去

marco.sh
```bash
#!/bin/bash
dir=$(pwd)
echo $dir
```

polo.sh
```bash
#!/bin/bash
cd $dir

```
</details>
