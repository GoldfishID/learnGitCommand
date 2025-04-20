# Git & GitHub 使用筆記

## 🔰 初次使用 Git

```bash
# 初始化本地 Git 倉庫
git init

# 設定使用者資訊（只需設定一次）
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

---

## 🔍 基本狀態說明

- **Untracked**：未被 Git 追蹤的檔案
- **Tracked**：已追蹤的檔案
- **Staged**：已暫存的檔案
- **Committed**：已提交至版本庫

```bash
git status        # 詳細狀態
git status -s     # 簡潔模式
git status -b     # 顯示分支狀態
```

---

## ✅ 基本操作流程

### ➕ 加入暫存區（Untracked → Staged）

```bash
git add 檔案名         # 個別加入檔案
git add .              # 加入所有變更檔案
git add *.py           # 加入所有 Python 檔案
git add -u             # 加入所有已追蹤變更的檔案
```

### 💾 提交（Staged → Committed）

```bash
git commit -m "註解"
git commit -a -m "註解"    # 自動 add 再 commit
```

### ✏️ 修改最後一次提交

```bash
git commit --amend -m "新註解"
```

---

## 🕓 查看提交歷史

```bash
git log
git log --oneline
git log --oneline --graph
```

> 離開 log 請按 `q`

---

## 🔍 比對差異

```bash
git diff
git diff ID -- 檔案名
```

---

## ♻️ 撤銷與復原

```bash
git checkout -- 檔案名        # 撤銷檔案的修改
git checkout ID -- 檔案名     # 回到特定版本
git reset 檔案名              # 從暫存區移除（保留修改）
git reset --hard ID           # 重設到特定版本（不可逆）
```

---

## 🗑️ 刪除檔案

```bash
# 刪除檔案後
git add test.py
git commit -m "刪除檔案"
```

---

## 🚫 忽略檔案

在資料夾中建立 `.gitignore` 檔案，寫入欲忽略的內容：

```
*.png
*.py
test.py
```

---

## 🌿 分支操作

```bash
git branch               # 查看分支
git branch 分支名        # 建立分支
git checkout -b 分支名   # 建立並切換分支
git switch 分支名        # 切換分支（新語法）
```

### 🔀 合併分支

```bash
git merge 分支名 -m "註解"   # 將分支合併至當前分支
```

### 🧹 刪除分支

```bash
git branch -d 分支名
```

---

## 🚀 推送到 GitHub

```bash
git add .
git commit -m "註解"
git push origin 分支名
```

> 建立 Pull Request，請求將分支合併到主線分支  
> 主分支合併後，記得執行：  
```bash
git pull
```

---

## 🤝 與他人協作流程

1. 成為協作者後，複製 GitHub repository 的 HTTPS 連結
2. 在終端機輸入：

```bash
git clone https://github.com/xxx/yyy.git
cd 資料夾名
```

3. 拉取最新版本：

```bash
git pull
```

---

📌 備註：Git 是追蹤檔案變化（diff）的工具，不是單純追蹤檔案本身。
