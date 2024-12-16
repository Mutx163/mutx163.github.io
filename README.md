# 个人主页项目

这是一个基于 Express + MySQL 的个人主页项目，包含博客、作品展示等功能。

## 功能特点

- 响应式设计，支持移动端和桌面端
- 博客系统，支持 Markdown 编写
- 作品展示
- 留言板功能
- 后台管理系统
- 支持深色/浅色主题切换

## 技术栈

- 前端：HTML5, CSS3, JavaScript
- 后端：Node.js, Express
- 数据库：MySQL
- 部署：GitHub Pages (前端) + NAS/云服务器 (后端)

## 部署说明

### 前端部署 (GitHub Pages)

1. Fork 本仓库
2. 修改 `js/script.js` 中的 API 地址为你的后端服务器地址
3. 运行 `deploy.bat` 或 `deploy.sh` 部署到 GitHub Pages
4. 访问 `https://[你的用户名].github.io`

### 后端部署

#### NAS 部署
1. 安装 Node.js 和 npm：
   ```bash
   apt update
   apt install -y nodejs npm
   ```

2. 安装 PM2：
   ```bash
   npm install -g pm2
   ```

3. 上传后端代码到 NAS：
   ```bash
   # 创建项目目录
   mkdir -p /home/website/server
   # 上传代码到该目录
   ```

4. 安装依赖并启动：
   ```bash
   cd /home/website/server
   npm install
   npm start
   ```

5. 常用 PM2 命令：
   ```bash
   # 查看运行状态
   pm2 status
   
   # 查看日志
   pm2 logs personal-website
   
   # 重启服务
   pm2 restart personal-website
   
   # 停止服务
   pm2 stop personal-website
   ```

#### 云服务器部署
1. 准备一个支持 Node.js 的服务器
2. 安装 Node.js 和 MySQL
3. 克隆仓库到服务器
4. 安装依赖：`npm install`
5. 配置环境变量：
   ```bash
   cp .env.example .env
   # 编辑 .env 文件，填入数据库配置等信息
   ```
6. 初始化数据库：`npm run init-db`
7. 启动服务：`npm start`

### 配置说明

在管理后台的系统设置中：

1. 配置数据库连接信息
2. 配置 API 服务器地址
3. 保存并测试连接

## 开发说明

### 本地开发

1. 克隆仓库：
   ```bash
   git clone [仓库地址]
   cd [项目目录]
   ```

2. 安装依赖：
   ```bash
   cd server
   npm install
   ```

3. 启动开发服务器：
   ```bash
   npm run dev
   ```

4. 访问 `http://localhost:3000`

### 目录结构

```
├── server/          # 后端代码
│   ├── app.js      # 主应用文件
│   └── init-db.sql # 数据库初始化脚本
├── public/         # 静态资源
├── js/            # 前端 JavaScript
├── css/           # 样式文件
└── *.html         # 页面文件
```

## 更新日志

### 2024-01-20
- 添加后台管理系统
- 支持博客和作品管理
- 添加数据导入导出功能
- 添加 NAS 部署支持

### 2024-01-19
- 初始化项目
- 添加基础页面结构
- 实现数据库连接

## 许可证

MIT License