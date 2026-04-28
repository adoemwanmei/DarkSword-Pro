```

```

# DarkSword Pro Commercial Version

Latest Enhanced Version Released April 2026 + Perfect Commercial Backend

## Project Overview

DarkSword Pro is the industry's leading iOS security research exploit framework, designed specifically for professional red teams and security research teams. We provide a complete iOS 18.4 - 18.7 exploit chain, combined with a powerful commercial-grade C2 control backend, providing comprehensive support for your security testing needs.

## **Get Full Project**: **Telegram**: [https://t.me/Jeequan](https://t.me/Jeequan) (Technical support not free, 5000U)

> **Disclaimer**: This tool is for authorized security research and penetration testing only.

## Core Features

### Exploit Modules

| Feature Module       | Supported Versions | Description                 |
| -------------------- | ------------------ | --------------------------- |
| WebKit RCE           | iOS 18.4 / 18.6+   | Remote Code Execution       |
| Sandbox Escape       | iOS 18.4           | Bypass sandbox restrictions |
| Privilege Escalation | iOS 18.4 - 18.7    | Kernel-level read/write     |
| C2 Communication     | Configurable       | Custom command & control    |

### C2 Control Panel Features

| Feature Module        | Description                                                     |
| --------------------- | --------------------------------------------------------------- |
| Device Management     | Device list, online status monitoring, device info viewing      |
| Task Management       | Batch task delivery, task status tracking, task history         |
| Data Exfiltration     | Keychain reading, WiFi password extraction, contacts extraction |
| Remote Control        | Screenshot, camera control, file management, command execution  |
| Location Tracking     | Real-time location, location history                            |
| Information Gathering | Call history, SMS content, clipboard data                       |
| Dashboard             | Device statistics, task overview, exfiltration records          |
| Attack Logs           | Complete operation logs, attack record tracking                 |
| Device Map            | Geographic location visualization                               |

### Supported CVEs

| CVE ID         | Target Version | Component             |
| -------------- | -------------- | --------------------- |
| CVE-2025-31277 | iOS 18.4       | WebWorker JSC Exploit |
| CVE-2025-43529 | iOS 18.6+      | WebWorker JSC Exploit |

## Technical Architecture

### Exploit Chain Flow

```
┌─────────────────────────────────────────────────────┐
│ 1. Landing Page                                    │
│    - Hidden iframe loads attack page               │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 2. Frame Injection                                 │
│    - Inject version detection and module loader     │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 3. Version Adaptation                              │
│    - Auto-detect iOS version                       │
│    - Load corresponding RCE module                 │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 4. Remote Code Execution                           │
│    - WebKit exploit                                │
│    - JavaScriptCore execution environment          │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 5. Sandbox Escape                                 │
│    - Bypass iOS sandbox security restrictions      │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 6. Privilege Escalation                           │
│    - Kernel-level read/write primitives            │
│    - ICMPv6 Socket technique                       │
│    - IOSurface physical memory mapping             │
└─────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────┐
│ 7. Command & Control                              │
│    - Customizable C2 address                       │
│    - Data exfiltration and transfer               │
└─────────────────────────────────────────────────────┘
```

## Project Structure

```
darksword-final/
├── darksword/                    # Python 主模块 (后端核心)
│   ├── __init__.py
│   ├── api/                      # API 路由模块
│   │   ├── __init__.py
│   │   ├── admin.py              # 管理面板 API
│   │   ├── devices.py            # 设备管理 API
│   │   ├── postexploit.py        # 后渗透 API
│   │   ├── tasks.py              # 任务管理 API
│   │   ├── upload.py             # 文件上传 API
│   │   └── websocket.py          # WebSocket 实时通信
│   ├── static/                   # 前端静态文件
│   │   ├── app.js                # 前端应用逻辑
│   │   ├── index.html            # 管理面板主页
│   │   └── style.css             # 样式文件
│   ├── cli.py                    # CLI 命令入口
│   ├── config.py                 # 配置管理
│   ├── crud.py                   # 数据库 CRUD 操作
│   ├── database.py               # 数据库连接
│   ├── models.py                 # 数据模型定义
│   ├── payloads.py               # Payload 管理
│   ├── schemas.py                # Pydantic 数据模式
│   └── server.py                 # FastAPI HTTP 服务器
│
├── payloads/                     # Web Payloads (漏洞利用载荷)
│   ├── frame.html                # iframe 框架页
│   ├── index.html                # 入口页面
│   ├── log.html                  # 日志页面
│   ├── pe_main.js                # 主漏洞利用脚本
│   ├── rce_loader.js             # RCE 加载器
│   ├── rce_module.js             # RCE 模块 (通用)
│   ├── rce_module_18.6.js        # RCE 模块 (iOS 18.6)
│   ├── rce_worker.js             # RCE Worker (通用)
│   ├── rce_worker_18.4.js        # RCE Worker (iOS 18.4/18.5/18.7)
│   ├── rce_worker_18.6.js        # RCE Worker (iOS 18.6.x)
│   ├── sbx0_main_18.4.js         # 沙箱逃逸主脚本 (iOS 18.4)
│   └── sbx1_main.js              # 沙箱逃逸主脚本 (新版)
│
├── log/                          # 日志目录
│   ├── inject.log                # 注入日志
│   ├── server_*.log              # 服务器运行日志
│   └── 其他完成的.md             # 完成记录
│
├── 展示/                         # 展示文档
│   ├── ScreenShot_*.png          # 截图
│   └── 支持的设备.md             # 支持的设备列表
│
├── exfil/                        # 数据泄露接收目录 (空)
├── templates/                    # 着陆页模板 (空)
├── __pycache__/                  # Python 缓存
│
├── .gitignore                    # Git 忽略配置
├── darksword_c2.db               # SQLite 数据库
├── pyproject.toml                # 现代 Python 项目配置
├── README.md                     # 项目文档
├── requirements.txt              # 依赖列表
└── start_server.py               # 服务器启动入口
```

## Quick Start

Test Client
![Dashboard](zhanshi/sb/sb0001.png)

## Interface Display

### C2 Control Panel - Dashboard

![Dashboard](zhanshi/001.jpg)

### C2 Control Panel - Device List

![Device List](zhanshi/002.jpg)

### C2 Control Panel - Task Management

![Task Management](zhanshi/003.jpg)

### C2 Control Panel - Device Management

![Device Management](zhanshi/004.jpg)

### C2 Control Panel - Function Menu

![Function Menu](zhanshi/005.jpg)

### Device Support

![Demo 1](zhanshi/sb/sb.png)

## Use Cases

- Authorized penetration testing projects
- Red team operations
- iOS security research
- Exploit technology analysis

## Contact Us

For more information or full project access:

- **Telegram**: [https://t.me/Jeequan](https://t.me/Jeequan)

---

**Disclaimer**: This tool is for authorized use only. Unauthorized system testing may violate laws and regulations.
