# これまでの問題と解決方法

## 千葉工業大学 学内ネットワークでGitHubにSSH接続する

デフォルトのSSH接続を行おうとするとしようしているポートが大学の設定で閉じられているため他のポートを指定してあげる必要がある。

### ポート指定方法

非公開鍵をコピーする

```bash
pbcopy < ~/.ssh/id_rsa
```

エディターで以下のファイルを作成

```bash
vi ~/.ssh/config
```
以下を入力する。
```
Host github.com
  HostName ssh.github.com
  IdentityFile ~/.ssh/id_rsa
  Port 443
  User git
```
入力したら保存する。

また、ファイル例が [git_memo/ubuntu/config](https://github.com/MibuchiYuta/git_memo/blob/master/ubuntu/config) にある。

### 動作確認

```bash
ssh -T git@github.com
```

