# ollama-setup

## 参考にしたやつ

* WSL2とDockerに関するもの  
https://qiita.com/hoshimado/items/51c99ccaee3d4222d99d  
* WSL2でsu用のパスワードを設定する方法  
https://www.konosumi.net/entry/2022/06/12/154745  
* Zscaler環境下でWSL2を使う  
https://qiita.com/ichi-ken/items/5a04a732524c72ff809a

## 手順
* wsl2のインストール  
  PowerShellかコマンドプロンプトを管理者権限で開き、以下コマンドを入力
  ```
  wsl --install
  ```
  少し待つとインストールが完了するのでWindowsを再起動する

* ubuntuの設定
  再起動後、自動でコマンドプロンプトが開き、インストールが進行する。パスワードとユーザー名を設定するように求められるので設定する。

* Dockerデスクトップのインストール
  以下のリンクを辿ってdockerデスクトップをインストールする
  https://docs.docker.jp/docker-for-windows/wsl.html
