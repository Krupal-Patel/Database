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
