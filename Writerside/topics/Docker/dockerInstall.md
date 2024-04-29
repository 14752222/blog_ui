# 重新安装docker

如果执行 `sudo systemctl status docker` 提示 `Unit docker.service could not be found`，这意味着在您的系统上 Docker 服务的 Systemd 单元文件不存在，可能是因为 Docker 并未正确安装，或者安装过程中出现了问题。

您可以尝试重新安装 Docker，并确保安装过程中没有出现任何错误。以下是重新安装 Docker 的一般步骤：

1. **卸载 Docker**:

   首先，您可以尝试卸载当前的 Docker 安装。执行以下命令：

   ```bash
   sudo yum remove docker docker-ce docker-engine docker.io containerd runc
   ```

2. **删除 Docker 文件**:

   删除 Docker 的相关文件和目录：

   ```bash
   sudo rm -rf /var/lib/docker /etc/docker
   ```

3. **重新安装 Docker**:

   安装 Docker 的最新版本。您可以按照 Docker 官方文档中的指南进行安装：https://docs.docker.com/engine/install/

   通常，在 CentOS/RHEL 上安装 Docker 的命令如下：

   ```bash
   sudo yum install -y yum-utils
   sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
   sudo yum install docker-ce docker-ce-cli containerd.io
   ```

4. **启动 Docker 服务**:

   安装完成后，您可以尝试启动 Docker 服务：

   ```bash
   sudo systemctl start docker
   ```

5. **检查 Docker 版本**:

   最后，您可以再次检查 Docker 版本，确保它已经正确安装并正在运行：

   ```bash
   docker --version
   ```
