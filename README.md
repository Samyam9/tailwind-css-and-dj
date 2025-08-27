# Django-Tailwind

## 📦 Installation Steps

### Step 1: Install django-tailwind
```bash
pip install django-tailwind==3.8.0
```

### Step 2: Add "tailwind" to INSTALLED_APPS in settings.py

```
INSTALLED_APPS = [
    ...
    "tailwind",
]
```


### Step 3: Initialize Tailwind

```
python manage.py tailwind init
```


### Step 4: Name the Tailwind app (e.g. theme). Then add this app, eg theme to installed_apps in settings.py


### Step 5: Add these two lines to settings.py

```
TAILWIND_APP_NAME = 'theme'
NPM_BIN_PATH = "C:/Program Files/nodejs/npm.cmd"
```
##### Make sure to edit the npm path according to your own by checking the npm path with following command in cmd .
```
where npm
```


### Step 6: Install Tailwind dependencies

```
python manage.py tailwind install
```

## 🛠 Development Mode

### Step 7: Start Tailwind and Django servers

#### Run these two commands in different terminals .
```
python manage.py tailwind start
python manage.py runserver


```

## Usage Examples 

### Option 1: Extend Tailwind base template

```
{% extends 'base.html' %}
{% block content %}
    <h1 class="text-4xl text-center text-red-400">hello django and tailwind</h1>
{% endblock %}
```
#### also add {% block content %} and {% endblock %} in theme\templates\base.html

### Option 2: Use full HTML with Tailwind 
#### (No use of theme\templates\base.html in this method)

```
{% load static tailwind_tags %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    {% tailwind_css %}
</head>
<body>
    <h1 class="text-4xl text-center text-red-400">hello django and tailwind</h1>
</body>
</html>

```
#### 📝 POV: Always add {% load static tailwind_tags %} at the top and {% tailwind_css %} in the <head>. The rest is plain HTML.
