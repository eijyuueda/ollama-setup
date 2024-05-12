# ollama-setup

## 参考にしたやつ

* WSL2とDockerに関するもの  
https://qiita.com/hoshimado/items/51c99ccaee3d4222d99d  
* WSL2でsu用のパスワードを設定する方法  
https://www.konosumi.net/entry/2022/06/12/154745  
* Zscaler環境下でWSL2を使う  
https://qiita.com/ichi-ken/items/5a04a732524c72ff809a  
* ファイル共有について  
https://zenn.dev/osm_gunma/articles/93b0c4f6c37df7
* DIfyのセットアップ  
https://docs.dify.ai/getting-started/install-self-hosted/docker-compose

## WSLとDockerの設定
* wsl2のインストール  

powerShellかコマンドプロンプトを管理者権限で開き、以下コマンドを入力
```
wsl --install
```
少し待つとインストールが完了するのでWindowsを再起動する

* ubuntuの設定  
  
再起動後、自動でコマンドプロンプトが開き、インストールが進行する。パスワードとユーザー名を設定するように求められるので設定する。

* Dockerデスクトップのインストール

以下のリンクを辿ってdockerデスクトップをインストールする  
https://docs.docker.jp/docker-for-windows/wsl.html

* (以下ubuntu作業)dockerグループに自身を追加しておく
```
sudo usermod -aG docker $USER
```

* suユーザーのパスワードを設定する
  
設定しておくと何かと便利なので設定しておく。  
```
sudo su -
```
```
passwwd
```

* ファイル共有の確認

Windowsとubuntu間の共有ディレクトリを確認する。以下のコマンドを実行すると、Windowsのエクスプローラーが開くので、その中にある<ユーザー名>のディレクトリをピン留めとかしとく。(このディレクトリがubuntuのホームディレクトリにマウントされている)
```
cd
```
```
explorer.exe ..
```

## Ollamaのインストール

* Ollamaをインストールする
  
Dockerで整備する方法もあるが、今のところ致命的な依存関係が見つからないので直インストール
```
curl -fsSL https://ollama.com/install.sh | sh
```

## DIfyのインストール
* クローンする
```
git clone https://github.com/langgenius/dify.git
```

* 移動
```
cd dify/docker
```

* DIfyを立ち上げる
```
docker compose up -d
```

* DIfyをアップデートする
```
cd dify/docker
git pull origin main
docker compose down
docker compose pull
docker compose up -d
```
