# ローカル開発環境用のMySQLをDockerで

## 事前準備

### macOS (Docker for Mac)

- インストール
  - [Homebrew Cask](https://caskroom.github.io/)でインストールする場合
    ```
    brew cask install docker-for-windows -y
    ```
  - インストーラパッケージをダウンロードする場合  
    [ここ](https://download.docker.com/mac/stable/Docker.dmg)からダウンロードして実行
- 起動
  - アプリケーション に追加された Docker.app を実行  
    起動完了(タスクトレイのアイコンのアニメーションが止まる)のを待ちます  

### Windows 10 (Docker for Windows)
※Docker for Windowsを使用するにはWindows 10でかつHyper-Vの有効化が必要です

- インストール
  - [Chocolatey](https://chocolatey.org/)を使用してインストールする場合
    ```
    choco install docker
    ```
  - インストーラパッケージをダウンロードする場合  
　  [ここ](https://download.docker.com/win/stable/Docker%20for%20Windows%20Installer.exe)からダウンロードして実行
- 起動
  - スタートメニューから`Docker for Windows`を選択し、  
    起動完了(タスクトレイのアイコンのアニメーションが止まる)のを待ちます  
- 設定(初回のみ)  
  - タスクトレイアイコンを右クリック[Settings...]で設定画面を表示  
    [Shared Drives]で、使用するドライブのチェックボックスをチェックし[Apply]

### Windows (Docker Toolbox)

- インストール
  - [Chocolatey](https://chocolatey.org/)を使用してインストールする場合
    ```
    choco install docker-toolbox
    ```
  - インストーラパッケージをダウンロードする場合  
    [ここ](https://download.docker.com/win/stable/DockerToolbox.exe)からダウンロードして実行
- 起動
  - スタートメニューから`Docker Quick Start Terminal`を選択

## 使い方
Dockerを起動してください
ターミナル(またはcmd.exeやPowerShell)を起動し  
このリポジトリをcloneしたディレクトリに移動してください  
※Docker Toolbox を使用している場合は`Docker Quick Start Terminal`を使用します  
 表示されたIPアドレスを下記手順の`localhost`と読み替えてください

- 開始
  ```
  docker-compose up -d
  ```
- phpMyAdmin  
  Webブラウザで `http://localhost:8080` にアクセス

- 停止
  ```
  docker-compose stop
  ```

- cnfの内容やSQLを修正した場合
  ```
  docker-compose down
  docker-compose up -d
  ```

## 開発しているプロダクトから接続する

 |||
 |:---|:---|
 |Host|localhost|
 |Port|3306|
 |DB|sample|
 |User|test|
 |Pass|passwd|

 - Windows で Docker Toolbox を利用している場合は  
   Hostの値は Docker Quick Start Terminal 起動時に表示された IPになります
