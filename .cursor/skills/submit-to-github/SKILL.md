---
name: submit-to-github
description: 将代码提交并推送到 GitHub 的完整流程，包括 git add、commit、push 及冲突处理。在用户想要提交代码、推送到 GitHub、或同步到远程仓库时使用。
---

# 提交代码到 GitHub

## 快速流程

1. 查看状态：`git status`
2. 添加文件：`git add .` 或 `git add <文件路径>`
3. 提交：`git commit -m "提交说明"`
4. 推送：`git push origin <分支名>`

## 详细步骤

### 1. 提交前检查

```bash
# 查看当前修改
git status

# 如有远程更新，先拉取再推送
git pull origin main
```

### 2. 添加并提交

```bash
# 添加所有修改
git add .

# 或添加指定文件
git add path/to/file.js

# 提交（使用清晰的说明）
git commit -m "feat: 添加新功能" 
# 或
git commit -m "fix: 修复某问题"
```

### 3. 推送到 GitHub

```bash
# 推送到主分支
git push origin main

# 或当前分支
git push origin $(git branch --show-current)
```

## Commit 信息格式建议

- `feat:` 新功能
- `fix:` 修复 bug
- `docs:` 文档更新
- `style:` 代码格式（不影响逻辑）
- `refactor:` 重构
- `chore:` 构建/工具变动

## 常见问题

**推送被拒绝（需要先 pull）**
```bash
git pull origin main --rebase
git push origin main
```

**首次推送新分支**
```bash
git push -u origin <分支名>
```

**撤销未提交的修改**
```bash
git checkout -- <文件>   # 撤销工作区修改
git reset HEAD <文件>    # 取消暂存
```
