
# Azure DevOps版本控制及基礎git操作

## 關於 Azure DevOps

一套專案管理系統

## 使用git的好處

所以，到底 Git 有什麼厲害的地方，會讓這麼多人選擇它呢：

1. **免費、開源**

    Git 是由 Linux 核心的作者 Linus Torvalds 在 2005 年為了管理 Linux 核心程式碼，僅花了 10 天所開發出來的，至目前已有十幾年的歷史了。除了可免費使用外，整個 Git 的原始程式碼也可在網路上取得（當然 Git 的原始程式碼也是用 Git 在做版本控制的）。

2. **速度快、檔案體積小**

    如果你是使用「複製、貼上大法」來處理檔案，這些備份的目錄會很佔空間。而其它大部份的版控系統大多是記錄每個版本之間的差異，而不是完整的備份整個目錄，所以整個目錄的大小就不會快速的增加。

    而 Git 特別的設計，在於它並不是記錄版本的差異，而是記錄檔案內容的「快照」（snapshot），它可以讓 Git 在非常快速的切換版本。至於什麼是「快照」，在後面的章節會有更仔細的介紹。

3. **分散式系統**

    對我來說，這個可能是最大的優點了。在以往其它的版本控制系統，例如 CVS 或是 SVN 之類的集中式的版控系統（Centralize Version Control），都需要有一台專用的伺服器，所有的更新都需要跟這台伺服器溝通。也就是說，萬一這台伺服器壞了，或是沒有網路連線的環境，版本控制功能就沒辦法使用。

    而 Git 是一款分散式的版控系統（Distributed Version Control），雖然通常也會有共同的伺服器，但即使在沒有伺服器或是沒有網路的環境，依舊可以使用 Git 來進行版控，待伺服器恢復正常運作或是在有網路的環境後再進行同步，不會受影響。而且，事實上在使用 Git 的過程中，大多的 Git 操作也都是在自己電腦本機就可以完成。

# 下載Git
https://git-scm.com/download/win

 # `使用者設定`
```git
$ git config --global user.name "Kuma Chen"
$ git config --global user.email "Kuma@mail.tw"
```
檢查使用者資訊
```git
$ git config --list
user.name=Kuma Chen
user.email=Kuma@mail.tw
```
【狀況題】可以每個專案設定不同的作者嗎？

**將指令中的global換成local就可以針對該專案設定**
```git
 $ git config --local user.name Kuruma
 $ git config --local user.email Kuruma@mail.tw
```
# 從Azure DevOps建立儲存庫

# 連接儲存庫的方法
## Visual Studio
## Visual Studio Code
https://code.visualstudio.com/docs/editor/versioncontrol
## 終端機(terminal) 操作

# 指令/基本操作
>為什麼需要學習在終端機環境中使用指令操作，圖形介面拖拉就相當方便了
> 1. 因為每個工作環境都不一定能夠安裝圖形介面或使用。
> 2. 圖形介面軟體也有很多種，每一種的操作細節可能會有些不同。
> 3. 而指令操作是唯一可於不同環境、情境中皆能使用的方案。


終端機環境(terminal)
> powershell
> gitBash
- Windows 鍵 + X (Windows)
- 搜尋「terminal」(MacOS)

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

使用 Git 前必知：常用終端機命令列指令
- 切換目錄
> cd (取得目前所在的位置)
> cd 路徑 
> cd ..(回上一層)
- 列出該路徑中的所有檔案
> ls

---

# gitignore
> 有些檔案我不想放在 Git 裡面…

不只是比較機密的檔案，有時候一些程式編譯的中間檔或暫存檔，因為每次只要一編譯就等於產生一次新的檔案，對專案來說通常沒有實質的利用價值，像這樣的檔案其實也不會想讓它進到 Git 裡。

要做到這件事，只要在專案目錄裡放一個 .gitignore 檔案，並且設定想要忽略的規則就行了。如果這個檔案不存在，就手動新增它。
>忽略的檔案類型 .檔案類型
>.txt
>忽略的資料夾 資料夾名稱/
>node_modules/

# GUI推薦

> GitKraKen
> 

# 書籍/學習資源推薦

1. ## 最親切的Git入門教室
    - **出版社：** 碁峰資訊
    - **書號：** ISBN 978-986-502-527-4 

2. ## 連猴子都能懂的Git入門指南
    - https://backlog.com/git-tutorial/tw/

3. ## 為你自己學Git
    - https://gitbook.tw/



---
參考資料：
https://gitbook.tw/chapters/introduction/what-is-git.html
