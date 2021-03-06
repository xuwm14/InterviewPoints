# linux基础知识

### 一、命令行快捷编辑

* Ctrl+a  光标回到命令行首。
* Ctrl+e  光标回到命令行末。
* Ctrl+f  光标向右移动一个字符。
* Ctrl+b 光标向左移动一个字符。
* Ctrl+k  剪切光标处到行尾处的字符。（有删除的作用）
* Ctrl+u  剪切光标处到行首处的字符。（有删除的作用）
* Ctrl+w  剪切光标前的一个单词。（有删除的作用）
* Alt+d   剪切光标后的一个单词。（有删除的作用）
* Ctrl+y  粘贴Ctrl+k 、Ctrl+u、Ctrl+w、Alt+d 剪切/删除的文本。
* Ctrl+c 中断正在执行的任务命令或者删除整行。
* Ctrl+r  搜索命令行中使用过的命令记录。
* Ctrl+g  从正在执行Ctrl+r的搜索中退出。
* Ctrl+l  清除屏幕上所有内容，并开始新的一行。
* Ctrl+z  暂停正在运行行中的任务（**jobs可以列出所有暂停的任务，fg可以恢复暂停的任务**）

### 二、常用操作指令

1. **ls** 显示指定工作目录下之内容（列出目前工作目录所含之文件及子目录)。
   * `ls -a` 显示所有文件及目录
   * `ls -l `显示列出的文件的详细信息
   * `ls -t` 将文件依建立时间排序列出
   * `ls -r` 反向排序

2. **find** 用来在指定目录下查找文件。
   * `find . -name "*.log" `在当前目录及其子目录中查找后缀为.log的文件
   * `find . -ctime -20`将目前目录及其子目录下所有最近 20 天内更新过的文件列出
   * `find / -size +500M`寻找系统中文件大小大于500M的文件

3. **chmod** 修改文件的权限
   * `chmod 777 filename`修改filename的权限为所有人可以读、写和执行
   * `chmod -R 777 dic`修改dic目录和其下所有文件的权限为所有人可以读、写和执行

4. **file**用于辨识文件类型
5. **mv**用于为文件或目录改名、或将文件或目录移入其它位置。

| 命令格式         |                           运行结果                           |
| ---------------- | :----------------------------------------------------------: |
| mv 文件名 目录名 |                     将文件移动到目标目录                     |
| mv 目录名 目录名 | 目标目录已存在，将源目录移动到目标目录；目标目录不存在则改名 |
| mv 目录名 文件名 |                             出错                             |
| mv 文件名 文件名 |                   将源文件名改为目标文件名                   |

6. **rm**用于删除一个文件或者目录
   * -f 即使原档案属性设为唯读，亦直接删除，无需逐一确认。
   * -i 删除前逐一询问确认。
   * -r 将目录及以下之档案亦逐一删除。
7. **cp**命令主要用于复制文件或目录
8. **grep**命令用于查找文件里符合条件的字符串
   * **-n 或 --line-number** : 在显示符合样式的那一行之前，标示出该行的列数编号。
   * **-i 或 --ignore-case** : 忽略字符大小写的差别。
   * **-c 或 --count** : 计算符合样式的列数。
9. **cd**命令用于切换工作目录
10. **df**命令用于显示目前在Linux系统上的文件系统的磁盘使用情况统计，-h以人类可读的方式展示
11. **du**命令用于显示目录或文件的大小。
    * -s或--summarize 仅显示总计。
    * -h或--human-readable 以K，M，G为单位，提高信息的可读性。
    * -m或--megabytes 以1MB为单位。
12. **mkdir**命令用于建立名称为 dirName 之子目录。
    * `mkdir [-p] dirName` -p会确保目录新建成功，如果父目录不存在会自动新建父目录。
13. **pwd**命令用于显示工作目录。
14. **kill** 命令用于删除执行中的程序或工作，使用-9可以彻底杀死进程。
15. **ps**命令用于显示当前进程 (process) 的状态。
    * -au 显示较详细的资讯
    * -aux 显示所有包含其他使用者的行程
    * -w 显示加宽可以显示较多的资讯

16. **top**命令用于实时显示 process 的动态，按照程序消耗资源从高到低排序。
    * -c 显示程序执行的完整命令
17. **free**命令用于显示内存状态。
18. **netstat**命令用于显示网络状态。
    * -a或--all 显示所有连线中的Socket
    * -l或--listening 显示监控中的服务器的Socket
    * -n或--numeric 直接使用IP地址，而不通过域名服务器
    * -u或--udp 显示UDP传输协议的连线状况

### 其它内容

1. **文件权限详解：**drwxr-xr-x，其中第一个字符代表文件类型，-代表文件，d代表为文件夹。2-10的9个字符每三个为一组，分别代表当前用户、当前用户所在的组和所有其他组对文件的操作权限。r代表读权限，w代表写权限，x代表执行（或进入目录）的权限，无对应权限则表示为-。权限有编码rwx代表111即数字7，r-x代表101即数字5。所以777代表所有用户都拥有对该文件的读取、写入和执行权限。

