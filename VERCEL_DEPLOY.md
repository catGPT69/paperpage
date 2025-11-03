# Vercel 部署指南

## 📦 GitHub 仓库信息

- **仓库地址**：https://github.com/catGPT69/paperpage
- **状态**：✅ 代码已成功上传

---

## 🚀 Vercel 部署步骤

### 第一步：登录 Vercel

1. 访问 **https://vercel.com**
2. 点击右上角的 **"Sign Up"** 或 **"Log In"**
3. 选择 **"Continue with GitHub"**，使用您的 GitHub 账号登录

### 第二步：导入项目

1. 登录后，点击 **"Add New..."** → **"Project"**
2. 在项目列表中找到 **`catGPT69/paperpage`** 仓库
3. 点击 **"Import"** 按钮

### 第三步：配置项目（重要）

Vercel 会自动检测 Next.js 项目，但需要确认以下设置：

#### 项目设置：
- **Framework Preset**：应该自动检测为 "Next.js"
- **Root Directory**：保持默认 `./`（如果代码在根目录）
- **Build Command**：`npm run build`（自动设置）
- **Output Directory**：`.next`（自动设置）
- **Install Command**：`npm install --legacy-peer-deps` ⚠️ **重要！**

⚠️ **关键设置**：由于项目使用了 `--legacy-peer-deps`，需要：

1. 在项目设置中，展开 **"Environment Variables"**
2. 或者点击 **"Show Advanced Options"**
3. 在 **"Install Command"** 中填入：`npm install --legacy-peer-deps`

或者创建 `.npmrc` 文件（已完成）：
```
legacy-peer-deps=true
```

### 第四步：部署

1. 检查所有设置无误后
2. 点击 **"Deploy"** 按钮
3. 等待 2-3 分钟，Vercel 会自动：
   - 安装依赖
   - 构建项目
   - 部署到全球 CDN

### 第五步：获得访问地址

部署完成后：

1. 在项目仪表板中，您会看到一个 **部署成功** 的消息
2. 会显示您的网站地址，格式类似：
   ```
   https://paperpage.vercel.app
   或
   https://paperpage-[随机字符].vercel.app
   ```
3. 点击这个地址即可访问您的网站！

---

## 📝 后续更新

### 自动部署

- **自动部署已启用**：每次您向 GitHub 推送代码时，Vercel 会自动重新部署
- 无需手动操作，非常方便！

### 手动重新部署

如果需要手动触发部署：

1. 进入 Vercel 项目页面
2. 点击 **"Deployments"** 标签
3. 找到最新的部署记录
4. 点击右侧的 **"..."** 菜单
5. 选择 **"Redeploy"**

---

## 🔧 故障排除

### 如果部署失败

#### 1. 检查构建日志
- 在 Vercel 项目页面点击失败的部署
- 查看 **"Build Logs"** 了解错误原因

#### 2. 常见问题

**问题：依赖安装失败**
- 解决：确保 `.npmrc` 文件包含 `legacy-peer-deps=true`

**问题：构建错误**
- 解决：检查代码是否有语法错误
- 在本地运行 `npm run build` 测试

**问题：找不到文件**
- 解决：确保所有图片文件都在 `public/` 文件夹中
- 确保文件路径正确

### 检查媒体文件

确保以下文件已上传到 GitHub（在 `public/` 文件夹中）：

- paper1-image1.jpg 到 paper1-image4.jpg
- paper2-image1.jpg 到 paper2-image6.jpg
- paper3-image1.jpg
- paper3-video.mp4
- paper3-video-poster.jpg
- paper4-image1.jpg
- paper4-image2.jpg
- paper5-image1.jpg

如果文件太大无法上传到 GitHub：
- 可以考虑使用 GitHub LFS（Large File Storage）
- 或者将大文件（如视频）上传到云存储服务

---

## ✅ 部署检查清单

在部署前确认：

- [x] 代码已推送到 GitHub
- [ ] 所有图片文件在 `public/` 文件夹中
- [ ] 所有视频文件在 `public/` 文件夹中
- [ ] `.npmrc` 文件包含 `legacy-peer-deps=true`
- [ ] 本地测试 `npm run build` 成功
- [ ] 本地测试 `npm run dev` 运行正常

---

## 🌐 访问网站

部署完成后，您的网站可以通过以下方式访问：

1. **Vercel 提供的默认域名**：
   - `https://paperpage.vercel.app`

2. **自定义域名**（可选）：
   - 在 Vercel 项目设置中添加您的域名
   - 按照提示配置 DNS 设置

---

## 📞 需要帮助？

如果遇到问题：

1. 查看 Vercel 的构建日志
2. 检查 GitHub 仓库中的文件是否完整
3. 确认所有依赖都已正确安装

祝您部署顺利！🎉

