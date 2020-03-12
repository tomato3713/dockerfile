# Redmine

設置場所: ```/srv/redmine```

## 起動方法

ここで、${db_password}, ${db_root_password} を指定しないで起動した場合は、.env
にあるパスワードで起動されるはず。

```sh
DB_PASSWORD=${db_password} DB_ROOTPASSWORD=${db_root_password} docker-compose up -d
```


## docker-compose.yml の変更反映

```sh
docker-compose up -d
```

## Plugin, theme の導入手順

${repository URI} は、導入するプラグイン・テーマのGitHub RepositoryのURIを指定する。

```sh
docker exec -it redmine bash
git clone ${repository URI} plugins/${plugin_name}
git clone ${repository URI} public/themes/${plugin_name}
exit
docker-compose restart
```
