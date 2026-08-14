### 关键决策记录

| 时间 | 决策 | 原因 |
|---|---|---|
| Phase 0 | 选择 Python + FastAPI | 生态丰富，适合快速开发 |
| Phase 1 | 设计 6 模块架构 | 覆盖导入、清洗、分析、聚合、WebUI、导出 |
| 第一轮精简 | 砍掉 Telegram/Ollama/Insights/报告导出 | 大一作业复杂度控制 |
| 第二轮精简 | 砍掉异步 Worker/聚合器/多页面 | 进一步简化 |
| 第三轮精简 | 砍掉 Python 后端 | CI keyring 依赖无法解决 |
| 最终方案 | 纯静态 HTML | 零依赖，GitHub Pages 直接部署 |

### 失败与教训

| 问题 | 尝试的解决方案 | 结果 |
|---|---|---|
| CI keyring 无后端 | 安装 dbus，mock keyring | 仍失败 |
| web_app.py 导入 save_analysis | 更新 db.py | 修复 |
| pyproject.toml addopts 格式 | 改为列表格式 | 修复 |
| Makefile Tab 缩进 | CI 绕过 Makefile | 修复 |
| 测试文件与源码不同步 | 完整替换所有测试文件 | 部分修复 |
| 网页按钮无响应 | 从 HTMX 改为纯 JS | 修复 |

### 最终方案优势

- 零依赖：不需要安装 Python、pip、任何库
- 零配置：不需要 API Key、不需要 Docker
- 即时部署：GitHub Pages 一键部署
- 隐私安全：数据完全在浏览器本地处理
