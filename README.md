# 这里放一些开发会使用的工具
可以有安装包、配置文件、装机的一些命令、配置ssh、搭环境、node、nvm、git、Raycast（用于剪贴板）、Mac本身终端不好再装个Alacritty——版本Version 0.11.0 这个有文件需要配置、
分Mac和win，一般win系统没有bash,git,所以比Mac还要多安装一下。

## Windows装机软件

我用不惯这个压缩工具：[7-zip压缩]（https://sparanoid.com/lab/7z/）


---
## 在Windows系统中配置SSH并查看密钥的步骤如下：

### 1. 检查是否已安装OpenSSH客户端
- 打开“设置” > “应用” > “可选功能”。
- 在列表中找到“OpenSSH 客户端”，若未安装，点击“添加功能”进行安装。

### 2. 生成SSH密钥
1. 打开命令提示符或PowerShell。
2. 输入以下命令生成密钥：
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
3. 按提示选择保存路径（默认在 `C:\Users\你的用户名\.ssh\id_rsa`）和设置密码。

### 3. 查看SSH密钥
- **公钥**：默认路径为 `C:\Users\你的用户名\.ssh\id_rsa.pub`，可用记事本打开查看。
- **私钥**：默认路径为 `C:\Users\你的用户名\.ssh\id_rsa`，同样可用记事本查看。

### 4. 配置SSH
1. 将公钥添加到远程服务器的 `~/.ssh/authorized_keys` 文件中。
2. 使用以下命令连接远程服务器：
   ```bash
   ssh 用户名@远程服务器地址
   ```

### 5. 使用SSH代理（可选）
- 启动SSH代理：
  ```bash
  eval $(ssh-agent -s)
  ```
- 添加私钥：
  ```bash
  ssh-add C:\Users\你的用户名\.ssh\id_rsa
  ```

### 6. 验证连接
- 使用以下命令测试连接：
  ```bash
  ssh -T git@github.com
  ```

### 总结
- **公钥**：`C:\Users\你的用户名\.ssh\id_rsa.pub`
- **私钥**：`C:\Users\你的用户名\.ssh\id_rsa`

通过这些步骤，你可以在Windows上配置SSH并查看密钥。

---
## 如果 `C:\Users\EDY\.ssh\id_rsa` 已经存在，你可以使用以下命令查看 SSH 密钥的内容：

---

### 1. **查看私钥**
私钥文件是 `id_rsa`，可以使用以下命令查看：
```bash
type C:\Users\EDY\.ssh\id_rsa
```
或者使用 PowerShell：
```powershell
Get-Content C:\Users\EDY\.ssh\id_rsa
```

---

### 2. **查看公钥**
公钥文件是 `id_rsa.pub`，可以使用以下命令查看：
```bash
type C:\Users\EDY\.ssh\id_rsa.pub
```
或者使用 PowerShell：
```powershell
Get-Content C:\Users\EDY\.ssh\id_rsa.pub
```

---

### 3. **注意事项**
- **私钥 (`id_rsa`)**：必须妥善保管，不要泄露。
- **公钥 (`id_rsa.pub`)**：可以分享给需要 SSH 访问的服务器或服务（如 GitHub）。

---

### 4. **验证密钥是否可用**
你可以通过以下命令测试密钥是否配置正确：
```bash
ssh -T git@github.com
```
如果看到类似 `Hi username! You've successfully authenticated...` 的提示，说明密钥配置成功。

---

如果你需要重新生成密钥，可以使用以下命令（注意会覆盖现有密钥）：
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```


----
## 命令进入D盘
在 Windows 的命令行（命令提示符或 PowerShell）中，从 C 盘切换到 D 盘的文件夹，可以使用以下命令：

---

### 1. **切换到 D 盘**
直接输入 `D:` 并按回车：
```bash
D:
```

---

### 2. **进入 D 盘的某个文件夹**
假设你要进入 D 盘的 `Projects` 文件夹，可以使用 `cd` 命令：
```bash
cd D:\Projects
```

---

### 3. **一步切换到 D 盘的文件夹**
你也可以直接一步切换到 D 盘的某个文件夹，无需先切换到 D 盘：
```bash
cd /d D:\Projects
```
- `/d` 参数允许同时切换驱动器和目录。

---

### 4. **查看当前目录**
如果你想确认当前所在的目录，可以使用以下命令：
```bash
cd
```
或者：
```bash
echo %cd%
```

---

### 示例
假设你当前在 C 盘，想切换到 D 盘的 `Documents\Work` 文件夹：
```bash
cd /d D:\Documents\Work
```

---

### 总结
- 切换到 D 盘：`D:`
- 进入 D 盘的文件夹：`cd D:\文件夹路径`
- 一步切换驱动器和文件夹：`cd /d D:\文件夹路径`

----
## 学习命令行工具 Command-line utilities
在命令行中，像 `cd`、`echo`、`cat` 这样的命令属于 **命令行工具（Command-line utilities）**，它们可以归类为 **Shell 命令**（在 Windows 下是 `cmd.exe` 或 PowerShell，在 Linux/macOS 下是 Bash/Zsh 等）。  

---

## **1. 这些命令的分类**
### **（1）基本文件操作命令**
- `cd`（Change Directory）：切换目录  
  ```bash
  cd C:\Users\YourName  # 进入指定目录
  cd ..                # 返回上一级目录
  ```
- `dir`（Windows） / `ls`（Linux/macOS）：列出当前目录的文件  
  ```bash
  dir    # Windows 查看当前目录内容
  ls     # Linux/macOS 查看当前目录内容
  ```
- `type`（Windows） / `cat`（Linux/macOS）：查看文件内容  
  ```bash
  type file.txt  # Windows 查看文件内容
  cat file.txt   # Linux/macOS 查看文件内容
  ```

### **（2）文本操作命令**
- `echo`：输出文本  
  ```bash
  echo "Hello, World!"  # 打印文本
  echo %PATH%          # Windows 查看环境变量
  echo $PATH           # Linux/macOS 查看环境变量
  ```
- `find`（Windows） / `grep`（Linux/macOS）：查找文件内容  
  ```bash
  find "keyword" file.txt  # Windows 查找文件内容
  grep "keyword" file.txt # Linux/macOS 查找文件内容
  ```

### **（3）系统管理命令**
- `tasklist`（Windows） / `ps`（Linux/macOS）：查看运行进程  
  ```bash
  tasklist              # Windows 查看进程
  ps aux               # Linux/macOS 查看进程
  ```
- `shutdown`：关机/重启  
  ```bash
  shutdown /s /t 0     # Windows 立即关机
  shutdown -r now      # Linux/macOS 立即重启
  ```

---

## **2. 如何学习这些命令？**
### **（1）Windows 命令行学习**
- **`help` 命令**：查看所有可用命令  
  ```bash
  help
  ```
- **`命令 /?`**：查看某个命令的帮助（如 `cd /?`）  
  ```bash
  cd /?
  dir /?
  ```
- **推荐学习资源**：
  - [Microsoft 官方 CMD 文档](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
  - [Windows 批处理教程（BAT 脚本）](https://www.tutorialspoint.com/batch_script/index.htm)

### **（2）Linux/macOS 命令行学习**
- **`man` 命令**：查看命令手册  
  ```bash
  man ls     # 查看 ls 命令的详细用法
  man grep   # 查看 grep 命令的详细用法
  ```
- **`--help` 选项**：快速查看命令帮助  
  ```bash
  ls --help
  ```
- **推荐学习资源**：
  - [Linux 命令行教程（LinuxCommand.org）](http://linuxcommand.org/)
  - [The Bash Guide（更高级的 Shell 学习）](https://guide.bash.academy/)

### **（3）通用学习方法**
1. **每天学几个命令**，并动手尝试。
2. **用 `help` / `man` / `命令 --help` 查用法**。
3. **写脚本自动化任务**（如 `.bat` 批处理或 `.sh` Shell 脚本）。
4. **使用搜索引擎**（如搜索 "how to list files in cmd" 或 "Linux find file by name"）。

---

## **3. 练习示例**
### **（1）Windows 练习**
```bash
# 进入 D 盘
D:

# 创建一个文件夹并进入
mkdir MyFolder
cd MyFolder

# 创建一个文件并写入内容
echo "Hello, CMD!" > test.txt

# 查看文件内容
type test.txt

# 查找包含 "Hello" 的文件
find "Hello" test.txt
```

### **（2）Linux/macOS 练习**
```bash
# 进入家目录
cd ~

# 创建一个文件夹并进入
mkdir myfolder
cd myfolder

# 创建一个文件并写入内容
echo "Hello, Terminal!" > test.txt

# 查看文件内容
cat test.txt

# 查找包含 "Hello" 的文件
grep "Hello" test.txt
```

---

## **总结**
| **类型**       | **Windows 命令** | **Linux/macOS 命令** |
|--------------|----------------|-------------------|
| **切换目录**   | `cd`           | `cd`              |
| **列出文件**   | `dir`          | `ls`              |
| **查看文件**   | `type`         | `cat`             |
| **查找文本**   | `find`         | `grep`            |
| **查看帮助**   | `命令 /?`       | `man 命令`         |

**学习建议**：
- **多动手实践**，尝试不同的命令组合。
- **遇到问题就查文档**（`help` / `man`）。
- **逐步学习脚本编写**（`.bat` 或 `.sh`），提高效率。

如果你对某个命令特别感兴趣，可以告诉我，我会给出更详细的教程！ 🚀
