dbname: notesdb
dbuser: notesuser
userpw: notesPW
port:5432


Create a DB dump
```postgresql
pg_dump -U notesuser -d notesdb > notesdb_20230208.sql
```
Create a DB schema dump
```postgresql
pg_dump -U notesuser -W -s -F p -v -f notesdb.sql notesdb
```

