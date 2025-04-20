README.md文件，介紹檔案

#初次始用git 
建立project 的資料夾
在project 資料夾內開啟cmd 輸入git init
會在當下資料夾內建立一格.git 的資料夾
之後設定
git config --global user.email "you@example.com"
git config --global user.name "Your name"


#個人
將本地新內容push 到github 上
git add.
git commit -m "註解"
git push

#amend
其中git commit -m "註解" --amend
是把當前的修改合併到log 中最新的版本裡面


#與他人合作
成為協作者後，將repository 處存到本地端電腦
<> code ->HTTPS ->複製連結
在終端機上輸入git clone https....(連結)
下載好的repository 會變成子資料夾
需要cd 資料夾名稱 才能去前往編輯

經過上面操作，如果合作的repository 有新文件，在本地
git pull 就能將新文件處存到本地端電腦


'''
Untracked 未追蹤
Tracked 已追蹤
Staged 已暫存
Committed 已提交


git status  # 查看目前狀態
git status -s  # 簡潔模式
git status -b  # 顯示分支狀態


# Untracked -> Staged 
git add 檔案名稱 ,ex: git add test.py test2.py
git add .  # 將所有檔案加入暫存區
git add *.py  # 將所有.py檔案加入暫存區
git add -u  # 將所有修改過的檔案加入暫存區

# Staged -> Committed
git commit -m "註解"  # 提交到本地端的版本庫
git commit -a -m "註解"  # 先做add 的動作再提交
git

git log  # 查看提交歷史
git log --oneline  # 查看提交歷史
git log --oneline --graph  # 查看提交歷史(圖形化)
(案Q)quickly  # 退出查看提交歷史

ID編號來自 git log --oneline

git diff  # 查看當前工作目錄與暫存區的差異
git diff ID編號 -- 檔案名稱  # 查看當前工作目錄與暫存區的差異

# Modified -> Untracked
git checkout ID編號 -- 檔案名稱  # 切換到指定的版本
git checkout -- 檔案名稱  #撤銷修改的文件
需要注意之後要git commit -m "註解"  # 提交到本地端的版本庫

# 將暫存區的裡面的修改放進工作區裡面
git reset 檔案名稱
git reset --hard ID編號  # 重置到ID編號的版本(會刪除所有修改)(不可逆)

Git追蹤的是檔案的變化，而非檔案本身 

# 檔案的刪除
test.py 檔案刪掉，git status會顯示為Untracked
需要git add test.py
後 git commit -m "刪除檔案"
再git status後就會發現沒異狀

'''

'''
忽略檔案清單
在資料夾創建 .gitignore
將需要忽略的檔案或副檔名寫入 .gitignore
如： *.png , *py , test.py
# 這樣就會忽略所有的png檔案和py檔案和test.py檔案

# 建立分支
git branch  # 查看目前分支
git branch 分支名稱  # 建立分支

git checkout -b branch2  # 建立並切換到新分支
git checkout -b              branch2
    切換分支  建立並切分心分支 新分支名稱

git switch 分支名稱 #切換分支

# 合併分支
git merge -m "註解" 分支名稱
將分支名稱合併到當前分支

# 刪除分支
git branch -d 分支名稱



在新分支建立新文件後一樣
git add. -> git commit -m "註解" -> git push origin branch2    
其中origin是遠端的名稱，branch2是分支名稱
之後去github上面就會發現多了一個分支branch2

這時可以做pull request 讓其他人知道做了修改，並可以請求將這些變更合併到主線分支
此時主分支的人可以看到這個請求，並可以選擇合併或拒絕這個請求
如果同意合併後，並可以將分支刪除
同時記得在主分支的人，記得在本地端做git pull 將最新的版本拉下來

'''