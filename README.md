# 论文集网站

## 本地开发

### 启动开发服务器

```bash
npm run dev
# 或
pnpm dev
```

开发服务器启动后，在浏览器中访问：
- **本地访问**：http://localhost:3000

### 项目结构

- `app/page.tsx` - 主页面，包含所有论文内容
- `public/` - 静态资源文件夹（图片、视频等）

## 部署到互联网（让日本人访问）

### 方法一：使用 Vercel（推荐，最简单）

Vercel 是 Next.js 的官方推荐平台，完全免费且支持全球CDN加速。

#### 步骤：

1. **准备 GitHub 账号**
   - 如果没有，请先注册：https://github.com

2. **将代码上传到 GitHub**
   ```bash
   # 初始化 git 仓库（如果还没有）
   git init
   git add .
   git commit -m "Initial commit"
   
   # 在 GitHub 上创建新仓库，然后：
   git remote add origin https://github.com/你的用户名/论文网站.git
   git branch -M main
   git push -u origin main
   ```

3. **部署到 Vercel**
   - 访问：https://vercel.com
   - 使用 GitHub 账号登录
   - 点击 "New Project"
   - 选择你的仓库
   - Vercel 会自动检测 Next.js 项目
   - 点击 "Deploy"
   - 等待几分钟，部署完成

4. **获得访问地址**
   - 部署完成后，Vercel 会提供一个网址，例如：
   - `https://your-project.vercel.app`
   - 这个网址可以在全球任何地方访问

5. **自定义域名（可选）**
   - 在 Vercel 项目设置中可以添加自己的域名

### 方法二：使用 Netlify

1. 访问：https://netlify.com
2. 使用 GitHub 账号登录
3. 选择 "Add new site" → "Import an existing project"
4. 选择 GitHub 仓库
5. 构建命令：`npm run build`
6. 发布目录：`.next`
7. 部署完成，获得访问地址

### 方法三：使用自己的服务器

如果已经有服务器（如日本的VPS），可以：

```bash
# 构建生产版本
npm run build

# 启动生产服务器
npm start
```

## 添加媒体文件

在部署前，请确保将所有图片和视频文件放在 `public` 文件夹中：

```
public/
├── paper1-image1.jpg
├── paper1-image2.jpg
├── paper1-image3.jpg
├── paper1-image4.jpg
├── paper2-image1.jpg
├── paper2-image2.jpg
├── paper2-image3.jpg
├── paper3-image1.jpg
├── paper3-video.mp4
├── paper3-video-poster.jpg
├── paper4-image1.jpg
├── paper4-image2.jpg
└── paper5-image1.jpg
```

## 注意事项

1. **文件大小**：如果视频文件很大，建议压缩后再上传
2. **Git 忽略**：`.gitignore` 已经配置，不会上传 `node_modules`
3. **环境变量**：如果使用了环境变量，需要在 Vercel/Netlify 中配置

## 访问测试

部署完成后，可以：
- 在日本的朋友直接通过网址访问
- 测试所有功能是否正常
- 检查图片和视频是否能正常加载

