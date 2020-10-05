---
layout: default
---

<a id="toDo" name="ToDo"></a>
# ToDo

<!-- TOC -->
- [ToDo](# toDo)
    - [Web Test](index.html#WebTest "Web Test")
    - [GitHub ミラーリング(--mirror)](index.html#mirror "GitHub ミラーリング(--mirror)")
    - [GitHub ミラーリング(--bare)](index.html#bare "GitHub ミラーリング(--bare)")
    - [Ubuntu インストール手順](ubuntu.html "Ubuntu インストール手順")
    - [Choreonoidインストール手順（for Windows10）](cnoid4win.html "Choreonoidインストール手順（for Windows10）")
<!-- /TOC -->

<a id="webTest" name="Web Test"></a>
## Web Test
**<font color="Red">フォントテスト</font>**
* リスト1
  * リスト1-1
  * リスト1-2
1. 番号付きリスト
2. テスト
    1. テスト
    2. テスト
    
```php
function hello(){
  return "Hello World!!";
}
```

|ヘッダ1|ヘッダ2|ヘッダ3|
|:---|:---:|---:|
|1|2|3|

<a id="mirror" name="GitHub ミラーリング(--mirror)"></a>
## GitHub ミラーリング(--mirror)
1. ミラーオプションを使用してのミラーリング
``` bash
 # ミラーしたいリポジトリをクローン
 $ git clone --mirror https://github.com/${USER1}/${REPOSITORY}.git
```

2. クローンしたリポジトリに移動
``` bash
 # HEAD branches config description hooks info objects packed-refs refs が作成
 $ cd ${REPOSITORY}.git
```

3. ミラーリング先にリポジトリを追加
``` bash
 $ git remote add --mirror=push test https://github.com/${USER2}/${REPOSITORY}.git
```

4. ミラーリングリポジトリをpushする
``` bash
 # testは上記の --mirror=push test ・・・ の test を指定
 # プルリクを保持するための refs は ReadOnly のため上書きが拒否される（更新に問題はない）
 $ git remote update
 $ git push test
```
``` ShellSession
 Username for 'https://github.com': ${USER2}
 Password for 'https://${USER2}@github.com': 
 Counting objects: 3, done.
 Delta compression using up to 8 threads.
 Compressing objects: 100% (2/2), done.
 Writing objects: 100% (3/3), 677 bytes | 0 bytes/s, done.
 Total 3 (delta 1), reused 0 (delta 0)
 remote: Resolving deltas: 100% (1/1), completed with 1 local object.
 To https://github.com/${USER2}/${REPOSITORY}.git
    d1fb722..b68418c  master -> master
  ! [remote rejected] refs/pull/1/head -> refs/pull/1/head (deny updating a hidden ref)
 error: failed to push some refs to 'https://github.com/${USER2}/${REPOSITORY}.git'
```

5. 設定の確認
``` bash
 $ gedit config &
```

<a id="bare" name="GitHub ミラーリング(--bare)"></a>
## GitHub ミラーリング(--bare)
1. ベアオプションを使用してのミラーリング
``` bash
 # ミラーしたいリポジトリをクローン
 $ git clone --bare --config remote.origin.fetch='+refs/heads/*:refs/heads/*' --config remote.origin.mirror=true https://github.com/${USER1}/${REPOSITORY}.git
```

2. 以降は GitHub ミラーリング(--mirror) と同様
