## NOTE 
- Python: v3.8.10
- Work dir: /home/ubuntu/django/mysite


## STEPS


1. activate virtual env

``` bash
$ . env/bin/activate
```

2. Install requirements
``` bash
pip install -r requirements.txt
```

3. Migrate
``` bash
python manage.py migrate
```

4. Testing gunicorn
``` bash
gunicorn --bind 0.0.0.0:8000 mysite.asgi:application -k uvicorn.workers.UvicornWorker
```

5. Created service
/etc/systemd/system/gunicorn.service

6. Setup Nginx
- Stop Apache2
- Install Nginx
- Create config. file at "/etc/nginx/sites-available/syncware.nginx.conf"
