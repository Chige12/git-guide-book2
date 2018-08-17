# このリポジトリについて
Gitコマンドかるた付属の学習ガイドブックにて、使用例通りにコマンドを実行したサンプルです。  
使用例では、リポジトリ名が「文化祭準備」ですが、ここでは「git-guide-book」になっています。

# 実行コマンドの紹介
私はこの通りに実行しました。

## リポジトリの作成（Aさんがやってたこと）
1. デスクトップにフォルダを作る `mkdir git-guide-book`
2. フォルダ内に移動 `cd git-guide-book`
3. テキストファイル「sample-textfile.txt」を作成し、記述。
4. 説明書ファイル「README.md」を作成し、記述。（この文章を記述）
5. GitHubへアクセスし、New repository のボタンをクリック。
6. 入力欄にリポジトリ名 `git-guide-book` を入力してリポジトリを作成する。
7. コンソールに戻り、 `git init` を実行。  
    実行結果： `Initialized empty Git repository in C:/Users/***/Desktop/git-guide-book/.git/`
8. リモートと紐づけ ` git remote add origin https://github.com/Chige12/git-guide-book.git` 
9. `git add README.md ` を実行。
10. `git add sample-textfile.txt ` を実行。
11. `git status` でコミットされるファイルを確認。  
    実行結果：
    ```
    On branch master

    Initial commit

    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)

            new file:   README.md
            new file:   sample-textfile.txt
    ```
12. `git commit -m "first commit"` を実行。
13. `git push -u origin master` でリモートにプッシュ。

## 花の色を赤色から黄色に変更
1. `git pull` を実行。作業前に必ず実行するとよい。
2. `git branch` で現在のブランチを確認。  
    実行結果： `* master`
3. flowerブランチを作成して移動 `git checkout -b flower`  
    実行結果： `Switched to a new branch 'flower'`
4. 再度 `git branch` で確認。  
    実行結果：
    ```
    * flower
      master
    ```
5. 花の色を赤色から黄色に変更。
6. `git diff` を実行。  
    実行結果：  
    ```
    diff --git a/sample-textfile.txt b/sample-textfile.txt
    index 03f66a3..0489818 100644
    --- a/sample-textfile.txt
    +++ b/sample-textfile.txt
    @@ -1,7 +1,7 @@
    お花を貼る {
      設置場所: 教室の東から4番目の窓
      種類: チューリップ
    -  花びら: 赤
    +  花びら: 黄
    :
    ```
7. `Ctrl + C` で抜ける
8. `git add .`を実行。
9. `git status` で確認。
10. `git commit -m "お花を黄色に変更"` を実行
11. `git push origin flower` を実行。

## flowerブランチをmasterブランチにマージ
1. `git branch` で現在のブランチを確認。  
    実行結果：  
    ```
    * flower
      master
    ```
2. branchをmasterへ移動 `git checkout master`
3. 再度 `git branch` で現在のブランチを確認。  
    実行結果：  
    ```
      flower
    * master
    ```
4. マージする `git merge flower`  
    実行結果：  
    ```
    Updating 9d0f4c3..ffffde9
    Fast-forward
    README.md           | 23 ++++++++++++++++++++++-
    sample-textfile.txt |  2 +-
    2 files changed, 23 insertions(+), 2 deletions(-)
    ```
5. `git push origin master`
