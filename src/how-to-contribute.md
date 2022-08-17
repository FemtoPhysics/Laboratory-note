# How to Contribute Your Notes
作者: [yctai](brianyjtai1994@gmail.com), [yihung](johnsonlin0528.c@nycu.edu.tw), [weihong](https://github.com/Wei-Hong0211)
- - -
## 1. 準備 [Github](https://github.com) 工作環境
> 以下教學只包含 `Windows` 作業系統的部分，如果你正在使用 `macOS / Linux` 作業系統，請和 [yctai](brianyjtai1994@gmail.com) 聯絡。

### 1.1 網路上的部分
1. 首先，先到 [Github](https://github.com) 註冊一個你的帳號。
2. 然後用瀏覽器打開大家的**筆記原始檔**[存放區](https://github.com/FemtoPhysics/Laboratory-note.git) (`repo`)
	- `Laboratory-note` 是 `repo` 的名字，擁有者是 `FemtoPhysics`
	- 只有管理者有權限可以**直接**編輯 `repo`，而你可以利用 `Fork` **複製** 一個 `repo` 到自己的帳號以便自己編輯

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/001.png)

3. 在你成功**複製** (`Fork`) 後，你會擁有一個可以和原始 `repo` 同步 (`sync`) 的新的 `repo`

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/002.png)

### 1.2 自己電腦的部分
1. 首先，先下載 [Github](https://github.com)的桌面軟體 [`GitHub Desktop`](https://desktop.github.com)，並且登入你的 Github 帳號
	> 這不是功能最完整的桌面軟體，而是最好上手的

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/003.png)

2. 接著，你應該能在**右手邊**找到你剛剛 `Fork` 的 `repo`；如果沒有的話，你可以**重新整理**一下

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/004.png)

3. 接著，將剛剛我們 `Fork` 過的 `repo` 下載 (`clone`) 到你的電腦裡
	- 這裡下載 (`clone`) 的會是你 `<你的帳號>/Laboratory-note` 的版本，**不會**是原版的 `FemtoPhysics/Laboratory-note`
	- 下載 (`clone`) 到電腦中的也是 `<你的帳號>/Laboratory-note` 的複本，在電腦上做的任何改動**並不會自動同步**到遠端的 `<你的帳號>/Laboratory-note`

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/005.png)

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/006.png)
	> 這裡需要記住你的 `repo` 被 `clone` 到你電腦裡的位置 (`Local path`)，以便之後使用

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/007.png)

## 2. 上傳筆記
### 2.1 新增筆記
#### 2.1.1 新增電腦的筆記到 `<你的帳號>/Laboratory-note`
1. Github `repo` 本身有記錄狀態的機制，剛剛 `clone` 到電腦裡的 `repo` 和遠端的狀態是一致的，所以**左手邊** `Changes` 標籤中是**空**的狀態

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/008.png)

2. 完成你的新筆記並存放在 `...\GitHub\Laboratory-note\src\<筆記分類資料夾>\<筆記檔名>.md`

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/009.png)

3. 重新回到 `GitHub Desktop`，就會在**左手邊** `Changes` 標籤找到新的檔案

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/010.png)

4. 確認筆記內容沒有問題之後，按照步驟完成 `commit`
	1. 在 `commit` 標題輸入: `Add Note: <你的標題>`
	2. 在 `commit` 內容輸入: `Author: <你的匿稱>`
	3. 按 `Commit to main` 完成 `commit` (**Locally**)

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/011.png)

5. 剛剛送出的 `commit` 是在你的電腦的 `repo` 完成的，遠端的 `<你的帳號>/Laboratory-note` 並沒有被同步，還需要用 `Push` 完成遠端上傳

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/012.png)

6. 在 `History` 的標籤中確認你的 `commit` 沒有問題後，用 `Push origin` 上傳到遠端的 `<你的帳號>/Laboratory-note`
	> 只要還沒 `Push`，如果發現問題，都可以 `右鍵 -> undo commit` 取消你做的 `commit`，完成修改之後再重新 `commit` 即可 (步驟 4)

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/013.png)

7. 完成 `Push` 後會看到下方畫面。

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/014.png)

#### 2.1.2 同步 `<你的帳號>/Laboratory-note` 到 `FemtoPhysics/Laboratory-note`
1. 完成 `Push` 後，`<你的帳號>/Laboratory-note` 會有新的變化 → 點選 `1 commit ahead`

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/015.png)

2. 你能看到自己 `Push` 過的 `commit`，以及 `<你的帳號>/Laboratory-note` vs. `FemtoPhysics/Laboratory-note` 的狀態比較，確認顯示 `Able to merge` 後，點選 `Create pull request`

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/016.png)

3. 確認勾選 `Allow edits by maintainers` 後，點選 `Create`

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/017.png)

4. 如果 `Pull Request` 沒有問題，只要等到管理者完成 `Merge Pull Request` 後，新增的筆記就能在[這裡](https://hackmd.io/@brianyjtai1994/HyGZvCDT5/%2FHyGZvCDT5)看到。

	![](https://raw.githubusercontent.com/FemtoPhysics/Laboratory-note/main/src/img/018.png)