# 📚 LitBuddy – 本地文献智能管家

> 基于 OpenClaw + DeepSeek 的 AI 文献管理工具 | 批量解析 PDF | 智能标签 | 本地文献库

[![GitHub stars](https://img.shields.io/github/stars/Stev3295/LitBuddy)](https://github.com/Stev3295/LitBuddy/stargazers)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 🎯 产品定位

面向研究生、科研人员的本地文献管理助手。解决多篇论文信息分散、难以分类和检索的痛点，将繁琐的手工整理压缩为 **一键批量处理 + 可视化文献库**。

## 🧠 核心功能

- **批量解析**：指定文件夹，AI 自动识别所有 PDF 论文，精准提取标题、作者、摘要、关键词。
- **智能概括**：从实验方法与结论章节提取 150–200 字的核心内容，清洗乱码、去除引用标记，输出通顺语句。
- **中文标签**：基于论文内容生成 3–5 个中文主题标签，自动区分中英文文献。
- **DOI 去重**：通过正则提取 DOI，同一文献多次整理只保留最新版本。
- **本地文献库**：所有数据存储于 `literature_db.json`，支持增量更新，无需数据库。
- **可视化前端**：独立 HTML 页面，按标签筛选、全文搜索、点击查看详细方法/结论。

## 🛠️ 技术架构

- **AI 框架**：OpenClaw（开源 Agent 框架）
- **大模型**：DeepSeek API（也支持其他 OpenAI 兼容模型）
- **PDF 解析**：pdfplumber + PyMuPDF（双重解析，故障转移）
- **前端**：原生 HTML/CSS/JS，无依赖，双击即用
- **数据存储**：本地 JSON 文件，基于 DOI 去重

## 📸 效果预览

> 将你的截图放在 `screenshots/` 文件夹，并在此处替换路径。

![文献库主页](./screenshots/dashboard.png)
*文献库前端：按标签筛选、搜索、查看详情*

![AI 对话](./screenshots/chat.png)
*在 OpenClaw Web UI 中发送批量整理指令*

## 🚀 快速开始

### 前置要求
- Windows / macOS / Linux
- Python 3.8+（用于 PDF 解析库）
- OpenClaw 已安装并配置好 DeepSeek API

### 1. 安装 PDF 解析依赖
```bash
pip install pdfplumber PyMuPDF
