# Mac自带的Apache服务器默认首页在哪里？

如果通过浏览器访问 http://localhost/ 显示 “It works!”，说明你的 mac 上运行了一个 HTTP 服务器，通常是 macOS 自带的 Apache 服务器 (httpd)。以下是定位其安装位置和配置文件的方法：

**1. 检查 Apache 是否运行**

在终端中运行以下命令，确认 Apache 是否正在运行：

```bash
sudo apachectl status
```

如果显示类似于 Server running，说明 Apache 正在运行。

**2. 找到 Apache 的配置文件**

默认情况下，Apache 的配置文件路径是：

```bash
/etc/apache2/httpd.conf
```

**3. 确认默认网页路径**

打开 httpd.conf 文件后，查找 DocumentRoot 的配置项，这就是默认的网页目录。例如：

```bash
DocumentRoot "/Library/WebServer/Documents"
```

通常情况下，默认网页会放在 /Library/WebServer/Documents 文件夹中。

**4. 验证 “It works!” 文件**

默认情况下，“It works!” 的内容由 /Library/WebServer/Documents/index.html.en 文件提供。可以用以下命令查看文件内容：

```bash
cat /Library/WebServer/Documents/index.html.en
```

**5. 停止或重启 Apache**

如果需要停止或重启 Apache，可以使用以下命令：

**停止 Apache：**

```bash
sudo apachectl stop
```

**启动 Apache：**

```bash
sudo apachectl start
```

**重启 Apache：**

```bash
sudo apachectl restart
```

**总结**

​	1.	Apache 的主配置文件路径是 /etc/apache2/httpd.conf。

​	2.	默认的网页路径是 /Library/WebServer/Documents。

​	3.	如果需要修改配置或网页文件，可以直接编辑对应的文件。

​	4.	使用 apachectl 命令管理 Apache 的运行状态。



希望这些步骤能帮助你定位和管理这个 HTTP 服务器！
