# Git 指令與 GitHub 互動指南

---

## 🧰 常用 Git 指令整理

### 🔧 初始化與設定

```bash
git init                                   # 初始化 Git 倉庫
git config --global user.name "你的名字"     # 設定全域使用者名稱
git config --global user.email "你的信箱"   # 設定全域 Email
```

### 📁 狀態與追蹤

```bash
git status            # 查看目前狀態
git status -s         # 簡潔模式
git add 檔案名         # 加入單一檔案至暫存區
git add .             # 加入所有變更檔案
git commit -m "訊息"   # 提交暫存內容
git log               # 查看提交歷史
```

### 📝 修改與還原

```bash
git diff              # 查看檔案差異
git checkout -- 檔案名 # 還原修改
git reset 檔案名       # 從暫存區移除檔案
git reset --hard ID   # 回到指定版本（不可逆）
```

### 🌿 分支管理

```bash
git branch             # 查看分支
git branch 新分支       # 建立新分支
git checkout 新分支     # 切換分支
git checkout -b 新分支  # 建立並切換新分支
git merge 分支名        # 合併分支
git branch -d 分支名    # 刪除分支
```

### 🌐 遠端操作（GitHub）

```bash
git remote add origin 遠端網址         # 連接遠端 repo
git remote -v                          # 查看遠端設定
git push -u origin main                # 推送主分支到 GitHub
git pull origin main                   # 從 GitHub 拉取主分支
git clone 遠端網址                     # 複製整個遠端 repo 到本地
```

---

## 🔁 Git 與 GitHub 的互動流程

### 📦 將本地專案上傳到 GitHub（第一次）

1. **初始化專案**
```bash
git init
```

2. **設定使用者資訊**
```bash
git config --global user.name "你的名字"
git config --global user.email "你的信箱"
```

3. **加入檔案並提交**
```bash
git add .
git commit -m "初始化專案"
```

4. **連接 GitHub 遠端 repo**
```bash
git remote add origin https://github.com/你的帳號/你的repo.git
```

5. **推送到 GitHub**
```bash
git branch -M main
git push -u origin main
```

---

### 🛠️ 從 GitHub 下載並更新專案（與他人協作）

1. **Clone 遠端專案**
```bash
git clone https://github.com/帳號/repo.git
cd repo
```

2. **修改後的推送流程**
```bash
git add .
git commit -m "修改內容"
git push
```

3. **若遠端有更新，先拉下來**
```bash
git pull origin main
```

---

### 📌 備註

- 若遇到錯誤：「Updates were rejected」，請先拉下遠端：
```bash
git pull origin main --allow-unrelated-histories
```

- `.gitignore` 可排除不需追蹤的檔案：
```
*.log
*.pyc
node_modules/
```

---

## 🧭 完整流程總覽

1. 建立資料夾並 `git init`
2. 設定 Git 使用者資訊
3. 加入檔案 `git add .`
4. 提交檔案 `git commit -m "訊息"`
5. 連接 GitHub：`git remote add origin`
6. 上傳到 GitHub：`git push -u origin main`
7. 後續更新只需：`git add .` → `git commit` → `git push`
8. 如要與他人協作，先 `git pull` 再進行修改
