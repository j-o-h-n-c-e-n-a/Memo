* 接続文字列
    + Server=サーバー名;Database=データベース名;UID=ユーザーID;PWD=パスワード;Port=ポート番号;

* テーブル一覧取得
```PostgreSQL:テーブル一覧取得
SELECT
 psut.relname,
 pd.description 
FROM pg_stat_user_tables AS psut
 LEFT JOIN pg_description AS pd
   ON psut.relid = pd.objoid
  AND pd.objsubid = 0 
ORDER BY
 psut.relname
```

* テーブルカラム取得
```PostgreSQL:カラム取得
SELECT
 att.attnum AS column_order,
 att.attname AS column_name,
 att.attnotnull AS is_nullable,
 att.attndims AS is_array,
 CASE REPLACE(typ.typname,'_','') 
  WHEN 'bpchar' THEN 'char' 
  WHEN 'int4' THEN 'integer'
  WHEN 'int2' THEN 'smallint'
  ELSE REPLACE(typ.typname,'_','') 
 END AS data_type,
 CASE REPLACE(typ.typname,'_','') 
  WHEN 'bpchar' THEN att.atttypmod - 4 
  WHEN 'varchar' THEN att.atttypmod - 4 
  WHEN 'numeric' THEN (att.atttypmod - 4) / 65536 
  ELSE (CASE att.atttypmod WHEN -1 THEN att.attlen ELSE att.atttypmod END) 
 END AS column_length,
 CASE REPLACE(typ.typname,'_','') 
  WHEN 'numeric' THEN (att.atttypmod - 4) % 65536 ELSE 0 
 END AS column_precision,
 con.contype AS is_primary, 
 dsc.description AS column_comment 
FROM pg_class cls
 INNER JOIN pg_attribute att
    ON cls.oid = att.attrelid
   AND att.attisdropped = false
  LEFT JOIN pg_type typ
    ON att.atttypid = typ.oid
  LEFT JOIN pg_constraint con
    ON con.conrelid = cls.oid
   AND att.attnum = ANY(con.conkey)
  LEFT JOIN pg_description dsc
    ON att.attrelid = dsc.objoid 
   AND att.attnum = dsc.objsubid 
WHERE cls.relname = '" & tableName & "' 
AND att.attnum > 0 
ORDER BY att.attnum
```
* テーブルインデックス取得

```PostgreSQL:インデックス取得
SELECT
 pic.relname AS index_name,
 pi.indisprimary AS is_primary,
 pi.indisunique AS is_unique,
 pi.indkey::text AS index_key 
FROM pg_class pc
 INNER JOIN pg_index pi
   ON pc.oid = pi.indrelid
 INNER JOIN pg_class pic
   ON pi.indexrelid =pic.oid 
WHERE pc.relname = '" & strTable & "' 
ORDER BY
 is_primary DESC,
 index_name"
```

* ランダム値を生成する
```PostgreSQL:ランダム値を生成する例
select * from random(); --結果例:0.13224（実行する度異なる値が生成）

--範囲指定：最小値=1 , 最大値=100
select round(( random() * (1 - 100) )::numeric, 0) + 100; --結果例:77

--範囲指定：最小値=1 , 最大値=10,000
select round(( random() * (1 - 10000) )::numeric, 0) + 10000; --結果例:7000
```