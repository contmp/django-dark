# django-dark


## Preamble

This is just a fresh playground, stay tuned or feel free to contribute.

## Setup

```sh
pip install django-dark

```

## Integration

1) Add "dark" to your INSTALLED_APPS setting like this:

    ```python
    INSTALLED_APPS = [
        ...
        'dark',
    ]
    ```

2) Modify Django's base_site.html

    ```html
    {% block extrahead %}
        <link rel="shortcut icon" href="{% static 'favicon.png' %}" />
        <link href="/static/admin/css/dark.css" type="text/css" media="(prefers-color-scheme: dark)" rel="stylesheet">
    {% endblock %}
    ```
    Temaplte can be found here: site-packages/django/contrib/admin/templates/admin/base_site.html
    

3) Helper Classes

    If you are using tintable images (one colored icons), you can add the class "img-invertiable", which simply represents:

    ```css
    .img-invertiable {
        filter: invert(0.7)
    }
    ```


## Current Result

![Dark](https://github.com/contmp/django-dark/blob/master/demo/dark.png?raw=true)
![Light](https://github.com/contmp/django-dark/blob/master/demo/light.png?raw=true)


## Developer Notes

```sh
# alias sv="source .virtualenv/bin/activate"
# alias vv="mkdir .virtualenv && python3 -m venv .virtualenv && sv"
vv
sv
pip install -r requirements/common.txt

# Compile Examples
lesscpy -x dark/less/dark.less dark/static/admin/css/dark.css
watchmedo shell-command --wait --patterns="*.less" --recursive --command "lesscpy -V -x dark/less/dark.less dark/static/admin/css/dark.css"
watchmedo shell-command --wait --patterns="*.less" --recursive --command "lesscpy -V -x dark/less/dark.less dark/static/admin/css/dark.css && python manage.py collectstatic --noinput"

# Distribution
python setup.py sdist
twine upload --repository-url https://upload.pypi.org/legacy/ dist/*
```
