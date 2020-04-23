# SQLServer

## テーブル設定

### 外部キー参照をしているテーブルのレコードが変化したときに、規約で処理をさせる。
```
CREATE TABLE human 
   (
      id int,
      name varchar
   )
   
CREATE TABLE wallet
   (
      id int,
      name varchar,
      human_id int -- FK
   )

ALTER TABLE wallet
CONSTRAINT wallet_FK1 FOREIGN KEY (human_id)
        REFERENCES human (id)
        ON DELETE CASCADE -- 人間が消えたら財布も消える
        ON UPDATE CASCADE -- 人間が生まれ変わってidが変わったら、財布の持ち主のidも変わる
```

#### 参考
- https://docs.microsoft.com/ja-jp/sql/relational-databases/tables/create-foreign-key-relationships?view=sql-server-ver15
