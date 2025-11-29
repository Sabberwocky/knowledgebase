
## Apache
---
```bash
sudo apt-get install apache2
```
```bash
sudo service apache2 start
```
```bash
sudo apt install php libapache2-mod-php
```




## Postgres
---


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






## Python
---

