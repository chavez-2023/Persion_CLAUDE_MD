# Handoff 文档

> 用于跨设备、跨会话交接工作状态，确保上下文不丢失。

---

## 项目信息

- **仓库名**：persion-claude-md
- **远程地址**：git@github.com:chavez-2023/persion-claude-md.git
- **分支策略**：`dev` 开发，`main` 稳定版本
- **协作设备**：3 台电脑

---

## 当前状态

### 分支
- `main`：初始提交
- `dev`：当前开发分支，已推送

### 已完成
- [x] 仓库初始化（main + dev 分支）
- [x] SSH 密钥配置（Windows 主力机）
- [x] 远程仓库连接
- [x] 项目级 CLAUDE.md（基于 Karpathy 四原则）

### 进行中
- [ ] 另外两台电脑的 SSH + clone 配置
- [ ] 全局 ~/.claude/CLAUDE.md 同步到其他设备

### 待办
- [ ] 补充项目 README.md
- [ ] 根据实际使用持续优化 CLAUDE.md 内容

---

## 配置清单（新设备用）

| 步骤 | 命令/操作 |
|------|-----------|
| 生成 SSH 密钥 | `ssh-keygen -t ed25519 -C "邮箱" -f C:\Users\用户名\.ssh\id_ed25519_github` |
| 添加公钥到 GitHub | GitHub → Settings → SSH and GPG keys → New SSH key |
| 配置 SSH config | 追加 `Host github.com` 段，指定 IdentityFile |
| 验证连接 | `ssh -T git@github.com` |
| 克隆仓库 | `git clone git@github.com:chavez-2023/persion-claude-md.git` |
| 创建 dev 分支 | `git checkout -b dev origin/dev` |
| 配置 Git 用户 | `git config --global user.name "chavez-2023"` / `user.email "apchat2023@gmail.com"` |
| 多仓库配置 | 同一 GitHub 账户下，每个项目各自 `git remote add origin git@github.com:chavez-2023/<仓库>.git` 即可，无需改全局配置或新 SSH key |

---

## 关键决策记录

| 日期 | 决策 | 原因 |
|------|------|------|
| 2026-05-13 | 使用 dev + main 双分支 | dev 日常开发，main 只放稳定版本 |
| 2026-05-13 | 删除 master 分支 | 统一使用 main 作为主分支 |
| 2026-05-13 | 项目级 CLAUDE.md 基于 Karpathy 原则 | 与全局 CLAUDE.md 分工：全局管"你是谁"，项目管"怎么做" |
| 2026-05-16 | 同一 GitHub 账户多仓库各自配置 remote | 同一 SSH key + 同一用户身份可复用，`origin` 是项目级配置互不影响 |

---

*最后更新：2026-05-16*
