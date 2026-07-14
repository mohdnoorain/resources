> import sql file to db

psql -d your_local_db_name -f backup.sql


> dump complete data with structure 

pg_dump "postgresql://username:password@host:port/database_name" -F p -v -f complete_backup.sql

> dump only structure

pg_dump "your_connection_string" -s -F p -v -f structure_only.sql

> dump compressed version

pg_dump "your_connection_string" -F c -v -f complete_backup.dump

> restore with compressed .dump file

pg_restore -d "postgresql://root:root@127.0.0.1:5432/new" --clean --no-owner --no-privileges -v complete_backup.dump
