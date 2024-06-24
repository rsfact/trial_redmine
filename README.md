# Redmine ローカル環境

```
docker-compose up
```

で、`http://localhost:8080`にアクセス。

管理者アカウント
ID: `admin`
PW: `admin`

PWリセットは、例えば、`admin12345`などにすればよい。


参考
https://zenn.dev/isi00141/articles/c8c883f7e33647


---

パターン2(現在はこちら)


立ち上げ
```
docker-compose up
```

(別ターミナルで)
プラグインのインストール

Easy Ganttを入れてみる。
解凍してpluginsフォルダに入れる。

```
docker-compose exec redmine bundle install
docker-compose exec redmine bundle exec rake redmine:plugins:migrate RAILS_ENV=production
docker-compose restart
```

後片付け(もうそのPCで使わない場合)
```
docker-compose down -v --rmi all
```


参考
https://zenn.dev/oppara/articles/docker-redmine
