# 🏘️ 智慧社区综合管理系统 (Smart Community Management System)

> **毕业设计 / 课程设计项目**  
> 基于 Spring Boot + Vue 的前后端分离智慧社区管理平台  
> 集成百度文心一言 AI 智能助手

[![License](https://img.shields.io/badge/license-MIT-green)](./LICENSE)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.6.6-brightgreen)](https://spring.io/projects/spring-boot)
[![Vue](https://img.shields.io/badge/Vue.js-2.6.11-blue)](https://vuejs.org)
[![Element UI](https://img.shields.io/badge/Element%20UI-2.15.6-409EFF)](https://element.eleme.io)

---

## 📖 项目概述

智慧社区综合管理系统旨在为社区居民提供便捷的生活服务和管理功能。系统采用 **前后端分离架构**，实现了用户管理、物业服务、社区交流、房屋租赁、闲置交易等核心模块，并集成了百度文心一言大模型，提供 AI 智能问答助手。

---

## ✨ 核心功能

### 👤 用户端
- **用户认证**：注册、登录、个人信息管理、密码修改
- **社区公告**：查看停水停电等通知信息
- **新闻资讯**：浏览社区动态和新闻
- **论坛交流**：发帖、回帖、点赞、收藏功能
- **房屋租赁**：发布房源、浏览租房信息、申请看房
- **闲置交易**：发布二手物品、浏览交易信息
- **物业服务**：在线预约物业维修、报修服务
- **个人中心**：我的收藏、个人设置、问题反馈

### 🔧 管理端
- **用户管理**：用户信息审核与管理
- **内容审核**：论坛帖子审核、租房信息审核、交易信息审核
- **公告管理**：发布和管理社区公告
- **资讯管理**：社区新闻发布与管理
- **物业预约管理**：处理用户的服务预约请求
- **数据统计**：系统运行数据概览

### 🤖 AI 智能助手
- 集成百度文心一言大模型
- 支持自然语言交互
- 智能页面导航推荐
- 关键词搜索联动
- 系统概况查询

---

## 🛠️ 技术架构

### 后端技术栈
| 技术 | 版本/说明 |
|------|-----------|
| 框架 | Spring Boot 2.6.6 |
| 数据库 | MySQL + MyBatis ORM |
| 分页插件 | PageHelper |
| JSON 处理 | Fastjson |
| 文件上传 | Commons FileUpload |
| AI 集成 | 百度千帆大模型 API |
| 端口 | **8888** |

### 前端技术栈
| 技术 | 版本 |
|------|------|
| 框架 | Vue.js 2.6.11 |
| UI 组件库 | Element UI 2.15.6 |
| 路由管理 | Vue Router 3.2.0 |
| 状态管理 | Vuex 3.6.2 |
| HTTP 客户端 | Axios 0.26.1 |
| 构建工具 | Vue CLI 4.5.13 |

---

## 📸 系统截图

> 请将你的实际截图放入 `screenshots/` 文件夹，并替换下方占位路径。

| 用户端首页 | 管理端首页 |
|:---:|:---:|
| ![用户端首页](./screenshots/user-home.png) | ![管理端首页](./screenshots/admin-dashboard.png) |

| 论坛交流 | AI 助手 |
|:---:|:---:|
| ![论坛](./screenshots/forum.png) | ![AI助手](./screenshots/ai-assistant.png) |

---

## 📁 项目结构

smart-community-management
├── 前端/scm-front/ # Vue.js 前端项目
│ ├── src/
│ │ ├── views/ # 页面组件
│ │ ├── router/ # 路由配置
│ │ ├── store/ # 状态管理
│ │ └── utils/ # 工具函数
│ └── package.json
├── 后端/smart-community-management/ # Spring Boot 后端项目
│ ├── src/main/java/com/zzl/smartcommunitymanagement/
│ │ ├── controller/ # 控制器层
│ │ ├── service/ # 业务逻辑层
│ │ ├── mapper/ # 数据访问层
│ │ ├── domain/ # 实体类
│ │ ├── ai/ # AI 聊天服务
│ │ └── config/ # 配置类
│ └── src/main/resources/
│ ├── mapper/ # MyBatis 映射文件
│ └── sql/ # 数据库脚本
└── README.md

---

## 🗄️ 数据库设计

系统包含 **18 个核心数据表**，涵盖用户信息、房屋管理、交易记录、论坛互动、物业服务等多个业务领域，采用规范化的数据库设计原则。  
初始化 SQL 脚本位于 `后端/smart-community-management/src/main/resources/sql/` 目录下。

---

## 🚀 快速开始（本地部署）

### 📥 1. 克隆仓库
git clone https://github.com/CZBN/smart-community-management.git
cd smart-community-management

⚙️ 2. 环境准备
确保你的本地环境已安装：
JDK 1.8 或更高版本
Node.js 14.x 或更高版本
MySQL 5.7 或更高版本
Maven 3.6 或更高版本

🗄️ 3. 数据库初始化
登录 MySQL，创建一个新数据库（例如 smart_community）：
CREATE DATABASE smart_community DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

导入项目中提供的 SQL 脚本：
mysql -u root -p smart_community < 后端/smart-community-management/src/main/resources/sql/init.sql

🔧 4. 后端配置
打开 后端/smart-community-management/src/main/resources/application.yml（或 application-dev.yml），修改数据库连接信息：
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/smart_community?useUnicode=true&characterEncoding=utf-8&serverTimezone=Asia/Shanghai
    username: your_username
    password: your_password
    如果有其他环境变量（例如百度千帆 API Key），也在此处或通过环境变量配置。

    ▶️ 5. 启动后端
cd 后端/smart-community-management
mvn spring-boot:run
后端服务启动后，运行在 http://localhost:8888。

🎨 6. 启动前端
cd 前端/scm-front
npm install
npm run serve
前端开发服务器启动后，访问 http://localhost:8081（或终端提示的地址）即可看到系统界面。

🤝 贡献与交流
作者：橙汁冰

邮箱：2915962508@qq.com

如果你对这个项目有任何建议或想法，欢迎提交 Issue 或 Pull Request。
📄 开源协议
本项目采用 MIT License。你可以自由使用、修改和分发，但请保留原作者信息。

如果觉得这个项目对你有帮助，请点一颗 ⭐️ Star 鼓励一下！
