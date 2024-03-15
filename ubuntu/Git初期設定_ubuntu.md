# ubuntuでのGit初期設定メモ

## インストール方法

```bash
sudo apt install git
```

## 鍵設定

### 端末(Terminal)上で鍵生成

```bash
ssh-keygen
```

以下、色々聞かれるが基本的にEnter

```bash
less ~/.ssh/id_rsa.pub
```
開いたらコピー
qキーでlessを閉じれる

### Githubに公開鍵を設定

1. <https://github.com/settings/keys> にアクセスし、New SSH Keyをクリック。
2. Title：SSH Keyがどの端末のものかわかるように入力(例：ThinkPad Ubuntu 20.04 Desktop)
3. Bodyにコピーしたテキストを 貼り付け
4. Add Keyをクリックし鍵の登録は終了
5.端末(Terminal)にて動作確認

    ```bash
    ssh -T git@github.com
    ```

    以下のように聞かれるので問題なければyes→Enter。

    ```
    # Are you sure you want to continue connecting (yes/no)?
    ```

    以下のような出力がされればOK

    ```
    Hi "username"! You've successfully authenticated, but GitHub does not
    # provide shell access.
    ```

### 利用方法


### 詳しくは以下のサイトが参考になる

- [お前らのSSH Keysの作り方は間違っている](https://qiita.com/suthio/items/2760e4cff0e185fe2db9)
