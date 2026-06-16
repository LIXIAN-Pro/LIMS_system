
<h1 align="center">🔬 LIMS — 环境监测实验室信息管理系统</h1>
<p align="center">
  <em>Laboratory Information Management System for Environmental Monitoring</em>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-blue?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/FastAPI-0.95+-009688?logo=fastapi" alt="FastAPI">
  <img src="https://img.shields.io/badge/Vue.js-3.x-4FC08D?logo=vuedotjs" alt="Vue.js">
  <img src="https://img.shields.io/badge/MySQL-8.0-4479A1?logo=mysql" alt="MySQL">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
</p>

---

## 📖 项目简介

**LIMS_system** 是一套面向环境监测实验室的现代化信息管理系统，采用前后端分离架构，实现了从**项目管理**、**任务分配**、**现场采集**、**样品入库**到**实验报告编制**的全流程数字化管理。

系统适用于环境监测站、第三方检测机构和科研实验室，帮助实验室提高运营效率、规范数据管理和确保数据可追溯性。

---

## ✨ 核心功能

| 模块 | 功能描述 |
|------|---------|
| 🔐 **用户认证** | JWT 令牌认证，权限分级管理（管理员 / 实验人员 / 采集人员） |
| 🏭 **实验室管理** | 实验室基本信息维护，安全分类管理 |
| 👥 **人员管理** | 实验人员信息录入、查询和管理 |
| 🏢 **委托单位** | 委托方（客户）信息管理 |
| 🚶 **采集人员** | 现场采集人员登记与调度 |
| 🔧 **设备管理** | 实验设备生命周期管理，设备台账 |
| 🧪 **试剂管理** | 化学试剂库存管理，出入库追踪 |
| 📋 **项目管理** | 检测项目全生命周期管理 |
| 📝 **采集模板** | 自定义采集表单模板 |
| ✅ **任务管理** | 采集任务分配、状态跟踪与提交 |
| 🧫 **样品管理** | 样品入库、流转与追踪 |
| 📊 **实验报告** | 实验报告生成、编制与管理 |
| 🏁 **项目结项** | 项目完成审核与归档 |
| ⚙️ **系统设置** | 全局系统配置管理 |

---

## 🏗️ 技术栈

### 后端
- **框架**: [FastAPI](https://fastapi.tiangolo.com/) — 高性能 Python Web 框架
- **数据库**: MySQL 8.0
- **ORM**: 原生 SQL + Pydantic 数据验证
- **认证**: JWT (JSON Web Token)
- **文件处理**: 支持上传 / 下载采集模板、实验报告、任务提交文件

### 前端
- **框架**: Vue.js 3.x
- **页面模块**: 实验室管理、采集管理、登录系统

---

## 📁 项目结构

```
LIMS_system/
├── index/                          # 前端页面
│   ├── Lab/                        # 实验室管理模块
│   ├── Gather/                     # 采集管理模块
│   └── login/                      # 登录页面
├── lims_backend/                   # 后端服务 (FastAPI)
│   ├── main.py                     # 应用入口，路由注册
│   ├── models.py                   # Pydantic 数据模型
│   ├── database.py                 # 数据库连接配置
│   ├── auth.py                     # JWT 认证模块
│   ├── routes/                     # 路由控制器
│   │   ├── auth.py                 # 用户认证接口
│   │   ├── lab_info.py             # 实验室信息接口
│   │   ├── personnel.py            # 实验人员接口
│   │   ├── entrust_units.py        # 委托单位接口
│   │   ├── collectors.py           # 采集人员接口
│   │   ├── equipment.py            # 设备管理接口
│   │   ├── agentia.py              # 试剂管理接口
│   │   ├── projects.py             # 项目管理接口
│   │   ├── collection_templates.py # 采集模板接口
│   │   ├── tasks.py                # 任务管理接口
│   │   ├── tasks_management.py     # 任务状态管理接口
│   │   ├── task_submissions.py     # 任务提交接口
│   │   ├── samples.py              # 样品管理接口
│   │   ├── experiment_reports.py   # 实验报告接口
│   │   ├── experiment_edit_reports.py  # 报告编制接口
│   │   ├── project_end.py          # 项目结项接口
│   │   └── system_settings.py      # 系统设置接口
│   ├── init_database.py            # 数据库初始化脚本
│   ├── init_database.sql           # 数据库结构定义
│   └── requirements.txt            # Python 依赖清单
└── uploads/                        # 文件上传存储
    ├── collection_templates/       # 采集模板文件
    ├── experiment_reports/         # 实验报告文件
    ├── experiment_edit_reports/    # 报告编制文件
    └── task_submissions/           # 任务提交文件
```

---

## 🚀 快速开始

### 环境要求

- Python 3.9+
- MySQL 8.0+
- Node.js 16+ (前端)

### 1. 克隆仓库

```bash
git clone https://github.com/LIXIAN-Pro/LIMS_system.git
cd LIMS_system
```

### 2. 安装后端依赖

```bash
cd lims_backend
pip install -r requirements.txt
```

### 3. 配置数据库

创建 MySQL 数据库:
```sql
CREATE DATABASE lims_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

编辑 `lims_backend/database.py` 配置数据库连接信息:
```python
DB_CONFIG = {
    "host": "localhost",
    "port": 3306,
    "user": "root",
    "password": "your_password",
    "database": "lims_db"
}
```

初始化数据库结构:
```bash
python init_database.py
```

### 4. 启动后端服务

```bash
python main.py
```

服务运行在 `http://localhost:8000`

📖 API 文档自动生成:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

### 5. 启动前端

```bash
cd index
python -m http.server 3000
```

访问 `http://localhost:3000` 进入系统。

---

## 🔗 API 概览

| 路径前缀 | 模块 |
|---------|------|
| `/api/auth` | 用户认证 |
| `/api/lab-info` | 实验室信息 |
| `/api/personnel` | 实验人员 |
| `/api/entrust-units` | 委托单位 |
| `/api/collectors` | 采集人员 |
| `/api/equipment` | 设备管理 |
| `/api/agentia` | 试剂管理 |
| `/api/projects` | 项目管理 |
| `/api/collection-templates` | 采集模板 |
| `/api/tasks` | 任务管理 |
| `/api/samples` | 样品管理 |
| `/api/experiment-reports` | 实验报告 |
| `/api/system-settings` | 系统设置 |

---

## 📄 License

本项目采用 [MIT License](LICENSE) 开源协议。

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

---

<p align="center">
  <b>如果这个项目对你有帮助，请给一个 ⭐ Star 支持一下！</b>
</p>
