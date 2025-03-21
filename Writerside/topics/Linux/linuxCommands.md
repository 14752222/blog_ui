# Linux常见命令

##### cd

- 参数
    - `-`：返回上一个目录
    - `.`：当前目录
    - `..`：上一级目录
    - `~`：用户主目录
- 示例
- `cd -`：返回上一个目录
- `cd .`：当前目录
- `cd ..`：上一级目录
- `cd ~`：用户主目录

##### ls

- 参数
    - `-a`：显示所有文件
    - `-l`：显示详细信息
    - `-h`：显示文件大小
    - `-r`：反向排序
    - `-t`：按时间排序
- 示例
- `ls -a`：显示所有文件
- `ls -l`：显示详细信息
- `ls -h`：显示文件大小
- `ls -r`：反向排序
- `ls -t`：按时间排序
- `ls -al`：显示所有文件和详细信息
- `ls -lh`：显示文件大小和详细信息
- `ls -lt`：按时间排序和详细信息
- `ls -lrt`：反向排序和按时间排序
- `ls -alh`：显示所有文件、详细信息和文件大小

##### pwd

- 参数
    - `-P`：显示物理路径
- 示例
- `pwd`：显示当前路径
- `pwd -P`：显示物理路径

##### cat

- 参数
    - `-n`：显示行号
    - `-b`：非空行显示行号
    - `-A`：显示控制符
    - `-E`：行尾显示$
    - `-T`：制表符显示^I
- 示例
    - `cat -n file.txt`：显示文件内容并显示行号
    - `cat -n -b file.txt`：显示文件内容并显示非空行号
    - `cat -A file.txt`：显示文件内容并显示控制符
    - `cat -E file.txt`：显示文件内容并显示行尾$
    - `cat -T file.txt`：显示文件内容并显示制表符^I

##### cp

- 参数
    - `-r`：递归复制
    - `-p`：保留文件属性
    - `-f`：强制复制
    - `-i`：交互复制
    - `-u`：更新复制
    - `-v`：显示复制进度
- 示例
- `cp -r dir1 dir2`：复制目录
- `cp -p file1 file2`：复制文件并保留文件属性
- `cp -f file1 file2`：强制复制文件
- `cp -i file1 file2`：交互复制文件
- `cp -u file1 file2`：更新复制文件
- `cp -v file1 file2`：显示复制进度

##### ps

- 参数
    - `-a`：显示终端上的所有进程
    - `-u`：显示用户的所有进程
    - `-x`：显示没有控制终端的进程
    - `-e`：显示所有进程
    - `-f`：显示完整格式
    - `-l`：显示长格式
    - `-w`：宽输出
    - `-r`：只显示正在运行的进程
- 示例
    - `ps -aux`：显示所有进程
    - `ps -ef`：显示完整格式
    - `ps -l`：显示长格式
    - `ps -aux | grep process`：查找进程
    - `ps -ef | grep process`：查找进程
