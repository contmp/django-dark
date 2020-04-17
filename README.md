# django-dark


## Preamble

This is just a fresh playground, stay tuned or feel free to contribute.

## Setup

```sh
pip install django-dark

```

## Integration

1) Add "dark" to your INSTALLED_APPS setting like this::

```python
INSTALLED_APPS = [
    ...
    'dark',
]
```

2. a) Modify Django's base_site.html

```html
<link href="/static/admin/css/dark.css" type="text/css" media="(prefers-color-scheme: dark)" rel="stylesheet">
```

2. b) Include base_site.html override Template here?


## Current Result

![Dark](https://github.com/contmp/django-dark/blob/master/demo/dark.png?raw=true)
![Light](https://github.com/contmp/django-dark/blob/master/demo/light.png?raw=true)


## Developer Notes

```sh
vv
sv
pip install -r requirements/common.txt
lesscpy -x dark/less/dark.less dark/static/admin/css/dark.css
watchmedo shell-command --wait --patterns="*.less" --recursive --command "lesscpy -x dark/less/dark.less dark/static/admin/css/dark.css"
watchmedo shell-command --wait --patterns="*.less" --recursive --command "lesscpy -x dark/less/dark.less dark/static/admin/css/dark.css && python manage.py collectstatic --noinput"
python setup.py sdist
twine upload --repository-url https://upload.pypi.org/legacy/ dist/*
```
