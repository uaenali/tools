# 使用 GitHub 管理文件
GitHub 不仅可以存代码，也可以存储各种文件，比如你的本地文档、安装包、图片等。你可以使用 GitHub 来管理和访问这些文件，方法主要有以下几种：

---

## **方法 1：使用 Git 提交文件**
适用于 **长期维护** 或 **多人协作** 的场景。

### **1. 创建 GitHub 仓库**
1. 登录 [GitHub](https://github.com/)
2. 点击右上角 `+`，选择 `New repository`
3. 填写仓库名称，比如 `my-docs`
4. 选择 **Public（公开）** 或 **Private（私有）**
5. 勾选 `Initialize this repository with a README`（可选）
6. 点击 `Create repository`

### **2. 在本地克隆仓库**
打开终端（Mac）或 Git Bash（Windows），运行：
```sh
git clone https://github.com/你的GitHub用户名/my-docs.git
```
然后进入该目录：
```sh
cd my-docs
```

### **3. 将你的文档复制到仓库文件夹**
把你想要上传的文档拷贝到 `my-docs` 这个文件夹里。

### **4. 提交并推送到 GitHub**
```sh
git add .
git commit -m "上传我的文档"
git push origin main
```
这样，文档就上传到了 GitHub，你可以随时访问和下载。

---

## **方法 2：使用 GitHub 网页直接上传**
适用于 **少量文件** 或 **临时存储**。

1. 进入你的 GitHub 仓库页面
2. 点击 `Add file` → `Upload files`
3. 拖拽你的文件到页面中，或者点击 `choose your files` 选择文件
4. 填写提交信息，点击 `Commit changes` 即可

---

## **方法 3：使用 GitHub Releases（适合安装包等大文件）**
如果你的文件较大，比如安装包，可以用 GitHub Releases 来管理。

1. 进入 GitHub 仓库
2. 点击 `Releases` → `Draft a new release`
3. 填写 Tag（如 `v1.0`）、标题和描述
4. 在 `Attach binaries by dropping them here or selecting them` 处上传文件
5. 点击 `Publish release`

这样，你的安装包就可以通过 `Releases` 页面下载了。

---

## **方法 4：使用 GitHub Gist（适合小型文档或笔记）**
如果你只是存储小型文本（如代码片段、笔记），可以使用 [GitHub Gist](https://gist.github.com/)：

1. 进入 [GitHub Gist](https://gist.github.com/)
2. 粘贴你的文本
3. 选择 **Public（公开）** 或 **Secret（私密）**
4. 点击 `Create secret gist`

这样，你就可以随时访问你的文档。

---

### **总结**
- **长期存储/多人协作** → 用 `Git` 提交文件
- **少量文件，临时上传** → 用 `GitHub 网页上传`
- **大文件（如安装包）** → 用 `GitHub Releases`
- **小文本（代码/笔记）** → 用 `GitHub Gist`
