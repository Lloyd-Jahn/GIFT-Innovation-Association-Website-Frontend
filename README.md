# 🎨 溥渊未来技术学院科协网站 - 前端项目

> 上海交通大学溥渊未来技术学院科技协会 3D打印工坊预约系统前端实现

## 📋 项目简介

这是一个现代化的3D打印工坊预约系统前端项目，为上海交通大学溥渊未来技术学院科技协会开发。项目采用纯HTML+CSS+JavaScript实现，提供了完整的用户认证、预约管理和作品展示功能。

### ✨ 主要功能

- 🏠 **首页展示** - 动态加载新闻公告和作品展示
- 🔐 **用户认证** - 完整的登录/注册系统
- 📝 **3D打印预约** - 在线提交打印申请，支持材料选择和时间安排
- 👤 **用户中心** - 查看个人信息、申请记录和作品
- ℹ️ **关于页面** - 了解工坊和团队信息

## 🚀 快速开始

### 方式一：直接在浏览器中打开（用于快速预览）

1. 找到项目文件夹
2. 双击 `index.html` 文件，使用浏览器打开
3. 开始浏览！

**注意**：此方式可能存在部分功能限制（如API调用），建议使用本地服务器方式。

### 方式二：使用本地服务器

#### 使用 Python 内置服务器

如果你的电脑已安装 Python，这是最简单的方式：

```bash
# 进入项目目录
cd /Users/jiangyi/Desktop/科协网站前端搭建

# Python 3.x
python3 -m http.server 8000

# 或者 Python 2.x
python -m SimpleHTTPServer 8000
```

然后在浏览器中访问：`http://localhost:8000`

#### 使用 Node.js 服务器

如果你安装了 Node.js：

```bash
# 安装 http-server（首次使用需要安装）
npm install -g http-server

# 进入项目目录并启动服务器
cd /Users/jiangyi/Desktop/科协网站前端搭建
http-server -p 8000
```

然后在浏览器中访问：`http://localhost:8000`

#### 使用 VS Code Live Server

如果你使用 VS Code 编辑器：

1. 安装 "Live Server" 扩展
2. 右键点击 `index.html`
3. 选择 "Open with Live Server"

## 📂 项目结构

```
科协网站前端搭建/
├── index.html              # 主页
├── login.html              # 登录页面
├── register.html           # 注册页面
├── workshop.html           # 3D打印工坊预约页面
├── user.html               # 用户中心
├── about.html              # 关于我们
├── styles/                 # CSS 样式文件夹
│   ├── index.css           # 主页样式
│   ├── login.css           # 登录页样式
│   ├── register.css        # 注册页样式
│   ├── workshop.css        # 工坊页样式
│   ├── user.css            # 用户中心样式
│   └── about.css           # 关于页样式
├── images/                 # 图片资源
│   ├── icons/              # 图标（溥渊LOGO、科协LOGO）
│   └── 3d-printing/        # 3D打印作品展示图片
└── README.md               # 项目说明文档
```

## 🔗 页面导航关系

```
index.html (主页)
    ├─> login.html (登录)
    │       └─> register.html (注册)
    ├─> workshop.html (3D打印工坊)
    ├─> about.html (关于我们)
    └─> user.html (用户中心，需登录)
```

## 🎯 功能特性

### 1. 响应式设计
- ✅ 支持桌面端和移动端自适应
- ✅ 优雅的动画和过渡效果
- ✅ 现代化的UI设计

### 2. 前后端交互
所有页面都预留了后端API接口，以下是完整的API列表：

#### 用户认证相关
- `POST /api/login` - 用户登录
- `POST /api/signin` - 用户注册
- `POST /api/logout` - 退出登录
- `GET /api/user/status` - 检查登录状态

#### 用户信息相关
- `GET /api/user/info` - 获取用户基本信息
- `GET /api/user/applications` - 获取用户申请列表
- `GET /api/user/works` - 获取用户作品列表

#### 工坊功能相关
- `POST /workshop/index` - 提交3D打印申请
- `GET /api/workshop/works` - 获取作品展示图片

#### 新闻公告相关
- `GET /api/news/links` - 获取新闻列表

### 3. 表单数据格式

#### 登录表单 (POST /api/login)
```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

#### 注册表单 (POST /api/signin)
```json
{
  "email": "user@example.com",
  "studentId": "123456789",
  "username": "张三",
  "password": "password123"
}
```

#### 3D打印申请表单 (POST /workshop/index)
```json
{
  "print-file": "(file object)",
  "material": "PLA",
  "model": "PLA Silk",
  "color": "白色",
  "allowed_time": {
    "Monday": ["morning", "afternoon"],
    "Tuesday": ["morning"],
    "Wednesday": ["evening"]
  }
}
```

## 🎨 设计规范

### 颜色方案
- **主色调**: `#3b82f6` (蓝色)
- **次色调**: `#ef4444` (红色)
- **成功色**: `#10b981` (绿色)
- **警告色**: `#f59e0b` (橙色)
- **文本主色**: `#1e293b` (深灰)
- **文本次色**: `#64748b` (中灰)

### 样式特点
- 简洁的动画效果（仅使用颜色变化和简单过渡）
- 统一的圆角设计（12px border-radius）
- 优雅的阴影和渐变效果
- 响应式布局（支持移动端）

## 🔧 开发说明

### 技术栈
- **HTML5** - 页面结构
- **CSS3** - 样式设计（Flexbox, Grid布局）
- **JavaScript (ES6+)** - 交互逻辑
- **Font Awesome 6.4.0** - 图标库

### 浏览器兼容性
- ✅ Chrome (推荐)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ⚠️ IE 11 及以下不支持

## 📝 后续开发建议

### 前端优化
1. 添加表单验证提示
2. 实现文件上传进度显示
3. 添加页面加载动画
4. 优化移动端体验

### 后端集成
1. 实现所有API接口
2. 配置CORS跨域
3. 添加JWT认证
4. 实现文件上传功能

## 📞 联系方式

如有问题或建议，请联系：
- 📧 邮箱: lloyd_jahn@sjtu.edu.cn

## 📄 许可证

© 2025 溥渊科协网络管理系统. 保留所有权利.

---

**开发团队**: 上海交通大学溥渊未来技术学院科技协会

**最后更新**: 2025年2月14日
