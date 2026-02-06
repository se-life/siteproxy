# 推送到 GitHub 的步骤

## 1. 在 GitHub 创建新仓库

访问：https://github.com/new

设置：
- Repository name: `siteproxy-custom`
- Description: `Customized siteproxy with simplified homepage`
- Visibility: Private（推荐）
- 不要勾选任何初始化选项

## 2. 执行推送命令

在当前目录（siteproxy）下执行：

```powershell
# 添加远程仓库（替换 YOUR_USERNAME）
git remote add origin https://github.com/YOUR_USERNAME/siteproxy-custom.git

# 重命名分支为 main
git branch -M main

# 推送到 GitHub
git push -u origin main
```

## 3. 验证推送成功

访问你的仓库页面：
https://github.com/YOUR_USERNAME/siteproxy-custom

应该能看到所有文件已上传。

## 4. 后续更新

如果以后有修改，使用以下命令推送：

```powershell
git add .
git commit -m "描述你的修改"
git push
```

## 常见问题

### 问题 1：推送时要求输入用户名和密码

GitHub 已不再支持密码认证，需要使用 Personal Access Token (PAT)：

1. 访问：https://github.com/settings/tokens
2. 点击 "Generate new token (classic)"
3. 勾选 `repo` 权限
4. 生成 token 并复制
5. 推送时用 token 代替密码

### 问题 2：推送失败 - 权限被拒绝

使用 SSH 方式：

```powershell
# 生成 SSH 密钥（如果还没有）
ssh-keygen -t ed25519 -C "your_email@example.com"

# 添加 SSH 密钥到 GitHub
# 复制 ~/.ssh/id_ed25519.pub 的内容
# 访问 https://github.com/settings/keys 添加

# 修改远程仓库地址为 SSH
git remote set-url origin git@github.com:YOUR_USERNAME/siteproxy-custom.git

# 推送
git push -u origin main
```

### 问题 3：想要修改仓库名

```powershell
# 修改远程仓库地址
git remote set-url origin https://github.com/YOUR_USERNAME/NEW_REPO_NAME.git
```
