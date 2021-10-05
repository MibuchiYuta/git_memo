# ubuntuでのGit初期設定メモ

## git install

```bash
sudo apt install git
```

## git 鍵設定

### 端末(Terminal)上で鍵生成

```bash
cd ~/.ssh/
mkdir ~/.ssh # .sshが無い場合
ssh-keygen
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

- [千葉工業大学 学内ネットワークでGitHubにSSH接続する](https://github.com/MibuchiYuta/git_memo/blob/master/ubuntu/Git%E5%95%8F%E9%A1%8C%E3%81%A8%E8%A7%A3%E6%B1%BA%E6%96%B9%E6%B3%95_ubuntu.md#千葉工業大学 学内ネットワークでGitHubにSSH接続する)

## gitconfigの編集

```bash

```
