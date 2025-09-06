SQL

## CREATE, RENAME and DROP Database
  - CREATE DATABASE database_name;
  - RENAME DATABASE old_name TO new_name;
  - DROP DATABASE database_name;

  - CREATE TABLE table_name (col1 datatype, col2 datatype);
  - ALTER TABLE table_name <action>;
    - ALTER TABLE table_name ADD COLUMN <column_name> datatype:
    - ALTER TABLE table_name DROP COLUMN <column_name>;
   
    - CREATE TABLE table_name (
      col1 datatype,
      col2 datatype,
      CONSTRAINT <PK_Name> PRIMARY KEY(<pk key column list>));

    - ALTER TABLE table_name (
      ADD CONSTRAINT <PK_Name> PRIMARY KEY(<pk key column list>));

    - CREATE TABLE table_name (
      col1 datatype NOT NULL,
      col2 datatype,
      PRIMARY KEY (col1),
      CONSTRAINT <fk_name> FOREIGH KEY(col2) REFERENCES <key_table> (<key_column>));

    - ALTER TABLE table_name
      ADD CONSTRAINT <fk_name> FOREIGH KEY(col2) REFERENCES <key_table> (<key_column>);

    - CREATE INDEX <index_name> ON <table_name> (<col1_name>, <col2_name>, ...)

    - SHOW TABLEs FROM <database_name>
    - SHOW COLUMNS FROM <table_name>
