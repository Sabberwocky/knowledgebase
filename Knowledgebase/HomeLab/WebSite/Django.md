
## Virtual environment

setup virtual environment
```bash
pip3 install virtualenv
virtualenv myenv
source myenv/bin/activate
```

to deactivate the environment simply 
```bash
deactivate
```


---
## Python Project

create project
```bash
django-admin startproject projectname
```


---
## Application in the project

create an app
```bash
python manage.py startapp myapp
```

---

## Database migration

db model is defined in models.py
```python 
python manage.py makemigration
python manage.py sqlmigrate myapp 0001
python manage.py migrate
```
create admin user
```python
python manage.py createsueperuser
```

---
## Run Server

```python
python manage.py runserver 0.0.0.0:8000
```

```python
python manage.py runserver
```
