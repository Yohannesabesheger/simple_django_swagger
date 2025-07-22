# Simple Django Swagger Project

This project is a simple Django-based API with integrated Swagger documentation, deployed on [PythonAnywhere](https://www.pythonanywhere.com/).

## 🛠️ Setup and Deployment Steps

### 1. Project Initialization

* Created a simple Django project with Swagger support.
* Installed required dependencies.
* Generated `requirements.txt` using:

  ```bash
  pip freeze > requirements.txt
  ```

### 2. Version Control

* Pushed the project to a GitHub repository.

### 3. Deployment on PythonAnywhere

#### a. Setup

* Created an account on [PythonAnywhere](https://www.pythonanywhere.com/).
* Used the console to clone the GitHub project into the home directory:

  ```bash
  git clone https://github.com/yourusername/simple_django_swagger.git
  ```

#### b. Virtual Environment

* Created a virtual environment:

  ```bash
  mkvirtualenv --python=/usr/bin/python3.10 venv
  ```

* Activated the virtual environment and installed Django:

  ```bash
  pip install django
  ```

* Installed project dependencies from `requirements.txt`:

  ```bash
  pip install -r requirements.txt
  ```

#### c. WSGI Configuration

* Edited the WSGI file:
  `/var/www/yohannesmm_pythonanywhere_com_wsgi.py`

  ```python
  import os
  import sys

  # Add project path
  path = '/home/yohannesmm/simple_django_swagger'
  if path not in sys.path:
      sys.path.append(path)

  os.environ['DJANGO_SETTINGS_MODULE'] = 'simple_project.settings'

  from django.core.wsgi import get_wsgi_application
  application = get_wsgi_application()
  ```

#### d. Django Settings

* Edited the `settings.py` file to allow the PythonAnywhere domain:

  File:
  `/home/yohannesmm/simple_django_swagger/simple_project/settings.py`

  ```python
  ALLOWED_HOSTS = ['yohannesmm.pythonanywhere.com']
  ```

#### e. Final Steps

* Navigate to the **Web** tab in PythonAnywhere.
* Press **Reload** to apply the changes.
