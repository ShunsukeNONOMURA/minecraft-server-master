# minecraft server master
dockerでのminecraftのサーバー起動。  
[itzg/minecraft-server](https://docker-minecraft-server.readthedocs.io/en/latest/#using-docker-compose)を利用。

## 使い方
```
git clone https://github.com/ShunsukeNONOMURA/minecraft-server-master.git
docker compose up

# 起動後にdataフォルダが作成される
```

## よく触るパラメータ
### docker-compose.yml
| 項目                | 説明       | 例       |
| ------------------- | ---------- | -------- |
| environment.VERSION | バージョン | "1.20.4" |

### data/server.properties
| 項目       | 説明                               | 例       |
| ---------- | ---------------------------------- | -------- |
| difficulty | 難易度                             | easy     |
| gamemode   | ゲームモード                       | survival |
| level-name | ワールドの指定（配布ワールドなど） | world    |

### data/ops.json
管理者権限の設定。  

**設定例（ダミー）**
```
[
  {
    "uuid": "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
    "name": "name",
    "level": 4,
    "bypassesPlayerLimit": false
  }
]
```

**パラメータ**
| 項目                | 説明                                             |
| ------------------- | ------------------------------------------------ |
| uuid                | uuid。https://minecraftuuid.com/ で検索可能。    |
| name                | ユーザ名                                         |
| level               | 権限レベル                                       |
| bypassesPlayerLimit | ログインユーザ数が最大でもログインできるかどうか |

## その他
- https://nj-clucker.com/wp-content/php/portcheck.php
    - minecraftのポート開放チェッカー（デフォルト：25565の場合）