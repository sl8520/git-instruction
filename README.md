# GIT 常用指令

## 前置作業
#### 產生 SSH 公開金鑰
```bash
$ ssh-keygen
```
#### 查看生成的公開金鑰
```bash
$ cat ~/.ssh/id_rsa.pub
```

## 基本設定
#### 版本查詢
```bash
$ git version
```

#### 查詢設定列表
```bash
$ git config --list
```

#### 設定識別資料
```bash
$ git config --global user.name 'your name'
$ git config --global user.email 'your email'
```

## 新增本地數據庫
#### 於本地資料夾新增數據庫
```bash
$ git init
```

#### 複製遠端數據庫
```bash
$ git clone <repository URL>

# 指定分支
$ git clone <repository URL> -b <branch name>
```

## 檔案
#### 加入檔案到索引
```bash
$ git add <file name>
```

#### 加入全部檔案到索引
```bash
$ git add .
```

#### 查詢檔案狀態
```bash
$ git status
```

#### 查詢 commit 記錄
```bash
$ git log
```

#### 將索引提交到數據庫
```bash
$ git commit -m '更新訊息'
```

#### 查看異動
```bash
$ git diff
```

## 還原
#### 還原工作目錄與索引, 回到最新 commit 狀態
```bash
$ git reset --hard 
```

#### 單一檔案取消索引
```bash
$ git reset HEAD <file name> 
```

#### 全部檔案取消索引
```bash
$ git reset HEAD
```

#### 恢復單一檔案到最新 commit 狀態
```bash
$ git checkout <file name>
```

#### 刪除最近一次 commit
```bash
$ git reset HEAD^ --hard
```

#### 刪除最近一次 commit, 但保留異動內容
```bash
$ git reset HEAD^ --soft
```

## 分支
#### 顯示所有本地分支
```bash
$ git branch
```

#### 新增分支
```bash
$ git branch <branch name>
```

#### 切換本地分支
```bash
$ git checkout <branch name>
```

#### 合併分支到目前分支
```bash
$ git merge <branch name>
```

#### 刪除分支
```bash
$ git branch -d <branch name>
```

#### 將遠端分支拉下來
```bash
$ git fetch <repository> <branch name>
```

#### 將遠端分支拉下來並與本地分支進行合併
```bash
$ git pull <repository> <branch name>
```

#### 將本地分支推送到遠端分支
```bash
$ git push <repository> <branch name>
```

## 暫存
#### 暫時儲存當前檔案
```bash
$ git stash
```
**==Untracked 狀態的檔案預設沒辦法被 Stash，需要額外使用 -u 參數。==**

#### 瀏覽 stash 列表
```bash
$ git stash list
```

#### 將 stash 套用至目前分支
```bash
$ git stash apply <stash id>
```

#### 刪除 stash
```bash
$ git stash drop <stash id>
```

#### 套用最新一筆 stash 並刪除
```bash
$ git stash pop
```

#### 刪除全部暫存
```bash
$ git stash clear
```