* テーブル情報取得

```SQLServer:テーブル情報取得
SELECT
--    tables.name AS table_name,
--    schemas.name AS schema_name,
--    table_descriptions.value AS table_description,
    columns.column_id as column_order,
    columns.name AS column_name,
    CASE 
        WHEN columns.is_nullable = 1 THEN
            'Y'
        ELSE
            'N'
        END AS is_nullable,
    '' as is_array, 
    types.name AS data_type,
    CASE
        WHEN types.name in ('varchar', 'nvarchar', 'varbinary') and columns.max_length = -1 THEN
            'MAX'
        WHEN types.name in ('decimal', 'numeric') THEN
            CONVERT(NVARCHAR(10), columns.precision) + ', ' + CONVERT(NVARCHAR(10), columns.scale)
        WHEN types.name in ('binary', 'char', 'varbinary', 'varchar') THEN
            CONVERT(NVARCHAR(10),columns.max_length)
        WHEN types.name in ('nchar', 'nvarchar') THEN
            CONVERT(NVARCHAR(10),(columns.max_length / 2))
        WHEN types.name in ('datetime2', 'datetimeoffset', 'time') THEN
            CONVERT(NVARCHAR(10),columns.scale)
        ELSE
            ''
        END AS column_length,
--    'Identity(' + CONVERT(NVARCHAR(10), identity_columns.seed_value) + ', ' + CONVERT(NVARCHAR(10), identity_columns.increment_value) + ')' AS identity_set,
    CASE WHEN primary_keys.key_ordinal IS NOT NULL THEN 1 ELSE 0 END as is_primary,
--     CASE
--         WHEN unique_keys.key_ordinal is null THEN
--             CONVERT(bit, 'FALSE')
--         ELSE
--             CONVERT(bit, 'TRUE')
--         END AS is_unique,
    CASE 
        WHEN left(default_constraints.definition, 2) = '((' AND RIGHT(default_constraints.definition, 2) = '))' THEN
            SUBSTRING(default_constraints.definition, 3, LEN(default_constraints.definition) - 4)
        WHEN left(default_constraints.definition, 1) = '(' AND RIGHT(default_constraints.definition, 1) = ')' THEN
            SUBSTRING(default_constraints.definition, 2, LEN(default_constraints.definition) - 2)
        ELSE
            NULL
        END as column_default,
    column_descriptions.value AS column_comment
FROM
    sys.tables
-- INNER JOIN
--     sys.schemas
-- ON
--     tables.schema_id = schemas.schema_id
-- AND
--     schemas.name = @schema_name
-- AND
--     tables.name = @table_name
-- LEFT OUTER JOIN sys.extended_properties AS table_descriptions 
--   ON table_descriptions.class = 1
--  AND tables.object_id = table_descriptions.major_id
--  AND table_descriptions.minor_id = 0
INNER JOIN sys.columns
  ON sys.tables.object_id = sys.columns.object_id
INNER JOIN sys.types
  ON columns.user_type_id = types.user_type_id
LEFT OUTER JOIN sys.identity_columns
  ON columns.object_id = identity_columns.object_id
 AND columns.column_id = identity_columns.column_id
LEFT OUTER JOIN sys.default_constraints
  ON columns.default_object_id = default_constraints.object_id
LEFT OUTER JOIN sys.extended_properties AS column_descriptions
  ON column_descriptions.class = 1
 AND columns.object_id = column_descriptions.major_id
 AND columns.column_id = column_descriptions.minor_id
LEFT OUTER JOIN (
    SELECT
        index_columns.object_id,
        index_columns.column_id,
        index_columns.key_ordinal
    FROM sys.index_columns
    INNER JOIN sys.key_constraints
      ON key_constraints.type = 'PK'
     AND index_columns.object_id = key_constraints.parent_object_id
     AND index_columns.index_id = key_constraints.unique_index_id
    ) AS primary_keys
  ON columns.object_id = primary_keys.object_id
 AND columns.column_id = primary_keys.column_id
-- LEFT OUTER JOIN
--     (
--     SELECT
--         index_columns.object_id,
--         index_columns.column_id,
--         index_columns.key_ordinal
--     FROM
--         sys.index_columns
--     INNER JOIN
--         sys.key_constraints
--     ON
--         key_constraints.type = 'UQ'
--     AND
--         index_columns.object_id = key_constraints.parent_object_id
--     AND
--         index_columns.index_id = key_constraints.unique_index_id
--     ) AS unique_keys
-- ON
--     columns.object_id = unique_keys.object_id
-- AND
--     columns.column_id = unique_keys.column_id
WHERE tables.name = 'T_オーダー' 
ORDER BY
--    schema_name,
--    table_name,
    column_order
```