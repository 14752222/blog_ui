# 在 Linux 上，您可以使用以下命令根据端口查找正在运行的程序：

1. **netstat**:

   使用 `netstat` 命令可以查看当前系统上所有网络连接和监听的端口。您可以通过过滤特定端口来找到与之相关的程序。例如，要查找监听在端口 `8080` 上的程序，可以执行：

   ```
   sudo netstat -tuln | grep :8080
   ```

   这将显示监听在端口 `8080` 上的所有 TCP 连接，以及与之关联的 PID。

2. **lsof**:

   `lsof` 命令可以显示系统中打开的文件、套接字和进程等信息。通过指定端口号，可以查找到占用该端口的进程。例如，要查找端口 `8080` 的进程，可以执行：

   ```
   sudo lsof -i :8080
   ```

   或者，如果您只想获取进程的 PID，可以使用 `-t` 选项：

   ```
   sudo lsof -ti :8080
   ```

3. **ss**:

   `ss` 命令也可以用来查看系统中的套接字和进程。通过过滤特定端口，您可以找到正在使用该端口的进程。例如，要查找监听在端口 `8080` 上的程序，可以执行：

   ```
   sudo ss -tuln | grep :8080
   ```

##### 如果您的系统中没有 `lsof` 命令，您可以尝试使用其他方式来查找正在监听端口 `8000` 的程序。一种常用的方法是使用 `netstat` 结合 `grep` 命令。以下是使用 `netstat` 的另一种方法：

```
sudo netstat -tulnp | grep 8000
```

在这个命令中：

- `-p` 选项用于显示与每个网络连接相关联的 PID 和程序名称。
- `tuln` 分别表示显示 TCP 连接、UDP 连接、监听状态、以数字形式显示地址和端口号。
- `grep 8000` 用于过滤出监听端口为 `8000` 的行。

这将返回监听在端口 `8000` 上的程序的信息，包括 PID 和程序名称。

如果您没有 `lsof` 命令，并且上述方法仍无法找到相关信息，请检查您的系统是否具有其他类似的工具，或者尝试安装 `lsof` 命令。