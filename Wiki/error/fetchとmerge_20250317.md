# エラー
git push -> 
```
error: failed to push some refs to 'github.com:yu-ka3028/ToMore.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

## エラー文から読み取れること
- refs:参照
- ローカルとリモートで差がある

## 仮説
- readme作成していなかったが、rails newでファイル作成されている可能性

## 調査したいこと
- 方法：forceでpushするか、fetchとmergeでやるか
# 結果
- 個人開発で、理由もreadmeだったので強制pushでも良かったが後学のためfetchしてOK

  ```md
  # リモートとローカルに差があるとき
  - 丁寧にやるなら：fetch + merge = pull
    - リモートの状態をローカルに持ってくる
    `git fetch origin main`

    - ローカルの状態をマージ
    `git merge origin/main`

  - 強制pushもできる
    `git push -f origin main`
  ```

# 参考記事
https://qiita.com/chiiiiiiiiiiii/items/118a5b3237c78d720582
https://qiita.com/wann/items/688bc17460a457104d7d
