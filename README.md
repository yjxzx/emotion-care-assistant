# 实时识别情绪识并加以关怀

# 📆 第一阶段 · 第1周任务安排（2025年5月15日～5月18日）

## 🎯 项目名称：实时识别情绪并加以关怀系统

## 🧠 本周核心目标
- 明确系统结构与功能模块
- 初步调研 FER / DeepFace 等工具的可行性
- 撰写项目目标与技术路线草稿
- 完成项目功能图绘制与 Git 初始化

---

## ✅ 每日任务计划清单

### 🗓️ 5月15日（周四）
- [ ] 阅读并运行 FER 官方示例代码（GitHub: [justinshenk/fer](https://github.com/justinshenk/fer)）
- [ ] 尝试调用摄像头实现情绪检测测试（fer.Video()）
- [ ] 梳理 FER 支持的情绪种类，并记录识别精度及响应速度
- [ ] 记录使用中遇到的报错、环境依赖问题

---

### 🗓️ 5月16日（周五）
- [ ] 阅读 DeepFace 文档（GitHub: [serengil/deepface](https://github.com/serengil/deepface)）
- [ ] 对比 DeepFace 与 FER 的异同（精度、体积、依赖、语音支持）
- [ ] 查阅两篇与“实时情绪识别”相关的论文（建议使用 arXiv / Google Scholar）
  - 示例关键词：`real-time facial emotion recognition deep learning`
- [ ] 摘要笔记：记录论文中采用的方法、使用的数据集、适用场景

---

### 🗓️ 5月17日（周六）
- [ ] 绘制系统功能结构图（建议使用 draw.io）
  - 包括：摄像头采集 → 表情识别 → 情绪分类 → 安慰反馈（语音/音乐）→ 用户界面展示
- [ ] 将结构图导出为 `.png` 图片，保存至 `/picture/` 文件夹
- [ ] Markdown 中插入图片（用于 README.md 说明）
- [ ] 创建本地 Git 仓库（如未完成）并上传现有文档与图像资源

---

### 🗓️ 5月18日（周日）
- [ ] 撰写项目说明初稿（建议用 Word 或 Markdown）
  - 包含内容：
    - 项目背景与意义
    - 项目目标（识别 + 关怀）
    - 技术选型（FER / DeepFace / OpenCV / Flask）
    - 实现方式与系统框架图
- [ ] 项目文件夹结构初步整理（如创建 `src/`, `static/`, `templates/`, `docs/`, `picture/`）
- [ ] 更新 GitHub 仓库并推送项目初稿内容

---
