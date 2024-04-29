# docker常见问题

### WARN[0000] /code/excerpt_server/docker-compose.yaml: `version` is obsolete
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?

- 解决方法

警告消息中提到 `version` 字段已过时，这意味着您的 `docker-compose.yaml` 文件中使用了不再支持的版本字段。建议您更新 `docker-compose.yaml` 文件，将 `version` 字段更改为当前支持的版本。通常，最新版本的 Docker Compose 使用 `version: '3'` 或更高版本。您可以将您的文件修改为类似以下的格式：

```yaml
version: '3'
services:
  your_service_name:
    image: your_image_name
    # 其他配置项...
```

请将 `your_service_name` 替换为您的服务名称，`your_image_name` 替换为您的 Docker 镜像名称，以及根据您的需求添加其他配置项。

至于无法连接到 Docker 守护程序的问题，可能是由于 Docker 守守程序未运行或者您没有权限访问 Docker 守守程序的 Unix 套接字文件所致。您可以使用以下命令检查 Docker 守守程序的状态：

```bash
sudo systemctl status docker
```

如果 Docker 守守程序未运行，您可以使用以下命令启动它：

```bash
sudo systemctl start docker
```


### 如果您已经将 `docker-compose.yaml` 文件中的 `version` 字段改为 `3`，但仍然收到警告消息 `version is obsolete`，可能是因为还有其他地方使用了过时的配置。请确保您的 `docker-compose.yaml` 文件中除了 `version` 字段之外，其他的配置也是符合新版本的 Docker Compose 格式的。

另外，关于无法连接到 Docker 守护程序的问题，请执行以下步骤：

1. **检查 Docker 守守程序是否正在运行**：

   使用以下命令检查 Docker 守守程序的状态：

   ```bash
   sudo systemctl status docker
   ```

   如果 Docker 守守程序未运行，您可以使用以下命令启动它：

   ```bash
   sudo systemctl start docker
   ```

2. **检查权限问题**：

   确保您的用户具有适当的权限来访问 Docker 守守程序的 Unix 套接字文件 `/var/run/docker.sock`。您可以执行以下命令来检查文件权限：

   ```bash
   ls -l /var/run/docker.sock
   ```

   如果权限不正确，您可以使用 `sudo` 命令运行 Docker Compose，或者将您的用户添加到 `docker` 用户组中以获取访问权限：

   ```bash
   sudo usermod -aG docker your_username
   ```

   其中 `your_username` 是您的用户名。

3. **重新加载 Docker 守守程序**：

   如果 Docker 守守程序正在运行但仍无法连接，您可以尝试重新加载它：

   ```bash
   sudo systemctl reload docker
   ```

4. **重启 Docker 守守程序**：

   如果以上步骤都没有解决问题，尝试重启 Docker 守守程序：

   ```bash
   sudo systemctl restart docker
   ```


### docker-compose build WARN[0000] current commit information was not captured by the build  error="failed to read current commit information with git rev-parse --is-inside-work-tree"

- 解决方法
 
```Shell
export BUILDX_GIT_INFO=false

```
