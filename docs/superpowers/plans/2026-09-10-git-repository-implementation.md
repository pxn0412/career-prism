# 职业棱镜 Git 仓库实施计划

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 在桌面建立完整的“职业棱镜”本地 Git 仓库，并将初始基线推送到 GitHub 私有仓库 `pxn0412/career-prism`。

**Architecture:** 工作区保留为资料与中间文件区，桌面 `职业棱镜` 目录作为正式开发仓库。正式仓库携带项目约束、上下文、根资料、设计与实施计划，通过 `main` 分支连接 GitHub `origin`。

**Tech Stack:** Git、GitHub、Markdown、PowerShell

---

### Task 1: 建立正式仓库文件树

**Files:**
- Create: `C:/Users/27115/Desktop/职业棱镜/README.md`
- Create: `C:/Users/27115/Desktop/职业棱镜/.gitignore`
- Copy: `AGENTS.md`, `PROJECT_CONTEXT.md`, `references/`, `docs/superpowers/`

- [ ] **Step 1: 验证目标目录状态**

运行 `Test-Path -LiteralPath 'C:/Users/27115/Desktop/职业棱镜'`。预期为 `False`；若为 `True`，先检查内容，避免覆盖已有文件。

- [ ] **Step 2: 创建目录并复制项目依据**

创建目标目录，将工作区中的约束、上下文、两份根资料、设计与计划复制到对应位置。复制后比较根资料 SHA256，预期源文件与目标文件哈希一致。

- [ ] **Step 3: 创建仓库说明与忽略规则**

README 明确项目定位、首版三职业、当前状态和资料约束；`.gitignore` 忽略依赖、构建产物、环境变量、日志、编辑器与系统临时文件。

### Task 2: 初始化并提交 Git 基线

**Files:**
- Create: `C:/Users/27115/Desktop/职业棱镜/.git/`

- [ ] **Step 1: 初始化 main 分支**

运行 `git init -b main`。预期 `git branch --show-current` 输出 `main`。

- [ ] **Step 2: 配置仓库级提交身份**

设置 `user.name=pxn0412` 与 `user.email=2711502588@qq.com`，并确认全局配置未被改写。

- [ ] **Step 3: 检查并提交**

运行 `git diff --check`、`git add .`、`git commit -m "chore: initialize career prism repository"`。预期生成根提交且工作树干净。

### Task 3: 连接并验证 GitHub 远程仓库

**Files:**
- Modify: `C:/Users/27115/Desktop/职业棱镜/.git/config`

- [ ] **Step 1: 添加远程地址**

运行 `git remote add origin https://github.com/pxn0412/career-prism.git`，预期 `git remote -v` 显示相同的 fetch 与 push 地址。

- [ ] **Step 2: 推送 main**

运行 `git push -u origin main`。预期 Git Credential Manager 使用现有登录或打开授权窗口，推送成功并建立上游分支。

- [ ] **Step 3: 完成验证**

运行 `git status --short --branch` 与 `git ls-remote --heads origin main`。预期本地 `main` 跟踪 `origin/main`、工作树干净，远程返回 `refs/heads/main`。
