## 概要
- Qiitaの「[Laravelの開発環境をDockerを使って構築する][link1]」2回目の挑戦

## ウェルカムページを出せた手順
1. gitリポジトリ直下(`~/git/docker-laravel2`)に移動する。Qiitaのhandsonディレクトリのこと
1. 出来合いのリポジトリをクローンする
    ```
    git clone https://github.com/ucan-lab/docker-laravel.git
    cd docker-laravel
    cp .env-example .env
    docker-compose up -d --build
    ```
1. 今クローンした`docker-laravel`の.gitディレクトリを削除する。リポジトリが入れ子になってしまうため
1. `.env`を`.gitignore`から削除してgit管理する
1. Laravelプロジェクトを新規作成する
    ```
    docker-compose exec app composer create-project --prefer-dist "laravel/laravel=5.8.*" .
    ```
1. redisを入れる(よく知らん)
    ```
    docker-compose exec app composer require predis/predis
    ```
1. [http://localhost:10080][link2]にアクセスするとLaravelのウェルカムページが出る。


## cloneで再現 Windows->Ubuntu



[link1]:https://qiita.com/ucan-lab/items/17c806973e69792ada99
[link2]:http://localhost:10080