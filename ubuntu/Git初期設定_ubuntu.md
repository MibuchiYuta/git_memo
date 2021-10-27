# ubuntuでのGit初期設定メモ

## インストール方法

```bash
sudo apt install git
```

## 鍵設定

### 端末(Terminal)上で鍵生成

```bash
ssh-keygen
cd ~/.ssh/
```

以下、色々聞かれるが基本的にEnter

```bash
pbcopy < ~/.ssh/id_rsa.pub #公開鍵をコピー
```

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

### 千葉工業大学 学内ネットワークを利用する場合は以下の作業を追加で行う

- [千葉工業大学 学内ネットワークでGitHubにSSH接続する](https://github.com/MibuchiYuta/git_memo/blob/master/ubuntu/Git%E5%95%8F%E9%A1%8C%E3%81%A8%E8%A7%A3%E6%B1%BA%E6%96%B9%E6%B3%95_ubuntu.md#%E5%8D%83%E8%91%89%E5%B7%A5%E6%A5%AD%E5%A4%A7%E5%AD%A6-%E5%AD%A6%E5%86%85%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%A7github%E3%81%ABssh%E6%8E%A5%E7%B6%9A%E3%81%99%E3%82%8B)
