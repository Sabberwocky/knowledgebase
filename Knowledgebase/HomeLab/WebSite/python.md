
create dependeyfile:

```bash
pip freeze > requirements.txt
```

```python
python manage.py makemigrations
python manage.py migrate
```