# django-dark


This is just a fresh playground

## Planed Setup flow
```sh
pip install django-dark
```

## Integration

a) Modify Django's base_site.html

```html
<link href="/static/admin/css/dark.css" type="text/css" media="(prefers-color-scheme: dark)" rel="stylesheet">
```

b) Include base_site.html override Template here?

## Current Result

![Dark](https://github.com/contmp/django-dark/blob/master/demo/dark.png?raw=true)
![Light](https://github.com/contmp/django-dark/blob/master/demo/light.png?raw=true)


## Developer Notes

```sh
lesscpy -x less/admin/dark.less static/admin/css/dark.css
watchmedo shell-command --wait --ignore-pattern="public/" --patterns="*.less" -R -c "lesscpy -x less/admin/dark.less static/admin/css/dark.css"
watchmedo shell-command --wait --ignore-pattern="public/" --patterns="*.less" -R -c "lesscpy -x less/admin/dark.less static/admin/css/dark.css && python manage.py collectstatic --noinput"
```
