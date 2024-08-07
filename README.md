# Recipe-Tutorial
A django recipe tutorial - source: https://www.youtube.com/watch?v=cPfvhpdYaNY&amp;list=PLXuTq6OsqZjbCSfiLNb2f1FOs8viArjWy&amp;index=2&amp;ab_channel=DeeMc


## Setup Virtual Environment

### Create Environment

#### Daisy
- 'python -m venv .venv' 
    'python -m venv...' = command needed to set environment up
    'v.venv' = name of the folder created for the virtual environment
- Python git ignore will have some standard naming conventions already; if not, need to add manually
- No need to push the virtual environment up into Github because this is only to enable us to run it locclly. Once we've completed the cloud deployment, the host we're using, the VE will be on it there & will not be read from GitHub.

#### Chat GPT (used in this instance)
- In Terminal, Command 'pip install virtualenv'
- Navigate to project directory; Command 'virtualenv venv'


### Activate Environment

#### Daisy
- To activate the virtual environment, run: '.venv/Scripts/activate'
- (.venv) will be displayed in terminal at beginning of PS C:
- If not inside VE, will not be able to run application; if pip install pacakages, they will be installed globally if you're not in an active environment

#### Chat GPT (used in this instance)
- To activate the virtual environment, run: 'source venv/bin/activate'
- You should see (venv) appear at the beginning of your terminal prompt, indicating that the virtual environment is active.


### Install Dependencies

#### Daisy
- Install django 'pip install django' (4.1 used in example)
- Start django project: 'django-admin startproject main .'
    - space followed by . is to ensure that the project files are installed in the current directory; otherwise it creates another folder within the folder
- Created settings, base & manage.py 
    - manage.py = where the instructions go to execure django; do not delete or move
- Start app: 'python manage.py runserver'
- Link should open successful application


#### Chat GPT (mix of two used in this instance)
- Install django 'pip install django'
- Generate requirements.txt: 'pip freeze > requirements.txt'
- Install Dependencies from requirements.txt: 'pip install -r requirements.txt'
- Update Dependencies: If you add new packages to your project, don't forget to update your requirements.txt by running 'pip freeze > requirements.txt' again.
- Start django project: 'django-admin startproject main .'
- Start app: 'python manage.py runserver'
- If the "Disallowed Host" page shows, copy & paste the cited HTTP Host & copoy into ALLOWED HOSTS in settings.py
- Try starting the app again


### Setup Environment Variables (Daisy)
- Store the SECRET_KEY in a VE, that will not be pushed to Github 
- Add import.os to settings.py
- Insert: SECRET_KEY = os.environ.get('SECRET_KEY')
- Import & create file env.py
- Add import os to env.py
- os.environ["SECRET_KEY"] = 'MASHupOFrandomWORDSnumbersANDsymbols'
- In settings.py, underneath BASE_DIR:
        if os.path.exists('env.py'):
            import env
- Hard refresh / use command 'python manage.py runserver' --> to ensure everything is still working


### Debug (Daisy)
- Debug needs to be true locally but it should be false in production. We don't want to have to continuously change this => set a new environment variable in settings.py:
    DEBUG = 'DEVELOPMENT' in os.environ
        - This will look in your environment for a variable called development. If it exist, DEBUG= True; if not, false
        - If you need to debug in production (when things work locally, but not in production), you can add to production environment & will show error messages
        - We don't want debug on in production because we don't want our error messages & potentially different variables (amongst other elements) from the back end being shown to the user. We would display proper error message pages instead, so the user knows something has gone wrong
- Create environment variable in env.py:
    os.environ["DEVELOPMENT"] = "True"
        - Because it is a string value, it doesn't really matter what you put in there (it's not a boolean - True or False in the line we set). 
        - The line is just looking for the presence. Type true anyways as it is reflective.

- Add env.py to gitignore
    - This file is to hide sensitive information & not available for the public to see
    - Should now be greyed out

