# lixian-space
My personal warehouse

这是一个基于FastAPI + Vue.js + MySQL的现代化环境监测实验室信息管理系统(LIMS)，提供完整的实验室管理、项目管理、任务分配、样品管理、实验报告等功能。

## 🏗️ 项目架构

LIMS-System/
├── index/                          # 前端页面目录
│   ├── Lab/                        # 实验室管理模块页面
│   ├── Gather/                     # 采集相关页面
│   └── login/                      # 登录页面
├── lims_backend/                   # 后端服务目录
│   ├── main.py                     # 主应用文件（应用初始化、路由注册）
│   ├── models.py                   # 所有Pydantic模型定义 - 数据结构和验证
│   ├── routes/                     # 路由模块目录 - Controller层
│   │   ├── __init__.py             # 路由包初始化
│   │   ├── auth.py                 # 用户认证路由 - 身份验证接口
│   │   ├── lab_info.py             # 实验室信息路由 - 实验室信息管理接口
│   │   ├── personnel.py            # 实验人员路由 - 人员管理接口
│   │   ├── entrust_units.py        # 委托单位路由 - 委托方管理接口
│   │   ├── collectors.py           # 采集人员路由 - 采集员管理接口
│   │   ├── equipment.py            # 设备管理路由 - 设备管理接口
│   │   ├── agentia.py              # 试剂管理路由 - 试剂库存管理接口
│   │   ├── projects.py             # 项目管理路由 - 项目信息管理接口
│   │   ├── collection_templates.py # 采集模板路由 - 采集表单模板管理接口
│   │   ├── tasks.py                # 任务管理路由 - 采集任务管理接口
│   │   ├── tasks_management.py     # 任务管理路由 - 任务状态管理接口
│   │   ├── task_submissions.py     # 任务提交路由 - 任务提交文件管理接口
│   │   ├── samples.py              # 样品管理路由 - 样品入库管理接口
│   │   ├── experiment_reports.py   # 实验报告路由 - 实验报告管理接口
│   │   ├── experiment_edit_reports.py # 报告编制路由 - 实验报告编制接口
│   │   ├── project_end.py          # 项目结项路由 - 项目完成管理接口
│   │   └── system_settings.py      # 系统设置路由 - 系统配置管理接口 
│   ├── database.py                 # 数据库配置 - 数据访问层
│   ├── auth.py                     # 认证模块 - JWT令牌生成和验证
│   ├── init_database.py            # 数据库初始化脚本 - 自动创建表结构和初始数据
│   ├── init_database.sql           # 数据库结构SQL - 完整的数据库表定义
│   ├── requirements.txt            # 依赖包列表 - 项目依赖管理
│   ├── README_数据库初始化.md       # 数据库初始化指南 - 详细的数据库配置说明
│   ├── python/                     # Python虚拟环境
│   └── __pycache__/                # Python缓存文件
└── uploads/                        # 文件上传目录
    ├── collection_templates/       # 采集模板文件存储
    ├── experiment_edit_reports/    # 实验报告文件存储
    ├── experiment_reports/         # 实验报告文件存储
    └── task_submissions/           # 任务提交文件存储
