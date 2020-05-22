

# [lecture 1 Course overview + the shell](https://missing.csail.mit.edu/2020/course-shell/)

### Exercises

<details>
    <summary>Create a new directory called missing under /tmp.</summary>

### 翻译

在tmp下面新建一个目录叫做missing

### 解答

```bash
cd /tmp
mkdir missing
```

</details>

<details>
    <summary>Look up the touch program. The man program is your friend.</summary>

### 翻译

查看touch命令 man命令会帮助你理解touch   

### 解答

```bash
touch 命令有两个作用
1. 创建一个新文件
2. 更改文件的时间标签为当前系统时间
```

</details>

<details>
    <summary>Use touch to create a new file called semester in missing.</summary>

### 翻译

用touch命令新建一个文件叫做 missing

### 解答

```bash
touch missing
```

</details>

<details>
    <summary>Write the following into that file, one line at a time: The first line might be tricky to get working. It’s helpful to know that # starts a comment in Bash, and ! has a special meaning even within double-quoted (") strings. Bash treats single-quoted strings (') differently: they will do the trick in this case. See the Bash quoting manual page for more information.</summary>

### 翻译

将以下代码写入文件。的一行是让代码正常运行的小技巧。# 后面是注释，！是有特殊含义的，即使在双引号因起来的字符串里面，bash对于单引号的处理比较特殊。。。。

### 解答

```bash
cat > touch
```

</details>

<details>
    <summary>Try to execute the file, i.e. type the path to the script (./semester) into your shell and press enter. Understand why it doesn’t work by consulting the output of ls (hint: look at the permission bits of the file).</summary>

### 翻译

试着去运行这段代码（通过在命令行输入 ./semester），通过看输出理解为什么不能运行（原因是权限问题）

</details>

<details>
    <summary>Run the command by explicitly starting the sh interpreter, and giving it the file semester as the first argument, i.e. sh semester. Why does this work, while ./semester didn’t?</summary>

### 翻译

通过sh semester命令运行程序，为什么这个成功了，但是 ./semester 不行呢？

### 解答

其实目前不太懂

</details>

<details>
    <summary>Look up the chmod program (e.g. use man chmod).
Use chmod to make it possible to run the command ./semester rather than having to type sh semester. How does your shell know that the file is supposed to be interpreted using sh? See this page on the shebang line for more information.</summary>

### 翻译

看看chmod命令，用此命令来让./semester 可以运行这个即哦阿本。为什么shell知道这个文件要用sh执行呢，看看page on the shabang line 吧

### 解答

```bash
# 给创建者 执行的权限
chmod u+x semester
# 运行
./semester
```

</details>

<details>
    <summary>Use | and > to write the “last modified” date output by semester into a file called last-modified.txt in your home directory.</summary>

### 翻译

用 |  > 来将semester的输出的最后一行写入的数据写入last-modified.txt

### 解答

```bash
./semester | tail -n 2 > last-modified.txt
```

</details>

<details>
    <summary>Write a command that reads out your laptop battery’s power level or your desktop machine’s CPU temperature from /sys. Note: if you’re a macOS user, your OS doesn’t have sysfs, so you can skip this exercise.</summary>
    
###  翻译

写一个指令，可以从/sys读出你电脑的电池余量或者cpu温度.如果你电脑没有sysfs，你可以跳过

### 解答

还没找到sysfs在哪。。。

</details>

