
# Azure DevOps版本控制及基礎git操作

# 從Azure DevOps建立儲存庫

# 連接儲存庫的方法
## Visual Studio
## Visual Studio Code
https://code.visualstudio.com/docs/editor/versioncontrol
## 終端機(terminal) 操作

```
終端機環境(terminal)
> powershell
> gitBash
- Windows 鍵 + X (Windows)
- 搜尋「terminal」(MacOS)
```

## 使用情境
1. ## 無法推送
    - **解決方法：** 先拉(pull)再推(push)

## 操作
- ### **Clone**
```
$ git clone 存放庫位置
```
- ### **儲存變更(Add)**
```
$ git add .
```
- Add單一檔案
- 撤銷已儲存變更
- 提交(Commit)
```
$ git commit -m '提交訊息'
```
---
- **從遠端提取至本地(Pull)**
```
$ git pull
```
- **取得遠端數據庫Fetch**

- **推送至遠端(Push)**
```
$ git push
```

**Fetch與Pull差異**

執行 pull，遠端數據庫的內容會自動合併。但是，有時候只是想確認遠端數據庫的內容卻不是真的想合併，在這種情況下，請使用 fetch。

執行 fetch，可以取得遠端數據庫的最新歷史記錄。取得的提交會導入在自動建立的分支中，並可以切換這個名為 FETCH_HEAD 的分支。

---
- **分支(Fork)**

- **切換分支**
```
$ git checkout 分支名稱
```
- **合併分支**

- **PR(Pull Request)**

- **衝突**
----
https://gitbook.tw/chapters/command-line/command-line.html

參考資料：
https://gitbook.tw/chapters/introduction/what-is-git.html
