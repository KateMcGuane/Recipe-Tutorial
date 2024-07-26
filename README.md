# Recipe-Tutorial
A django recipe tutorial - source: https://www.youtube.com/watch?v=cPfvhpdYaNY&amp;list=PLXuTq6OsqZjbCSfiLNb2f1FOs8viArjWy&amp;index=2&amp;ab_channel=DeeMc


## Setup Virtual Environment

### Create Environment

#### Daisy's Instruction
- 'python -m venv .venv' 
    'python -m venv...' = command needed to set environment up
    'v.venv' = name of the folder created for the virtual environment
- Python git ignore will have some standard naming conventions already; if not, need to add manually
- No need to push the virtual environment up into Github because this is only to enable us to run it loccally. Once we've completed the cloud deployment, the host we're using, the VE will be on it there & will not be read from GitHub.

#### Chat GPT (used in this instance)
- In Terminal, Command 'pip install virtualenv'
- Navigate to project directory; Command 'virtualenv venv'


### Activate Environment

#### Daisy's Instruction
- To activate the virtual environment, run: '.venv/Scripts/activate'
- (.venv) will be displayed in terminal at beginning of PS C:
- If not inside VE, will not be able to run application; if pip install pacakages, they will be installed globally if you're not in an active environment

#### Chat GPT (used in this instance)
- To activate the virtual environment, run: 'source venv/bin/activate'
- You should see (venv) appear at the beginning of your terminal prompt, indicating that the virtual environment is active.


### Install Dependencies

#### Daisy's Instruction
- Install django 'pip install django'
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
- Update Dependencies: If you add new packages to your project, don't forget to update your requirements.txt by running pip freeze > requirements.txt again.
- Start django project: 'django-admin startproject main .'
- Start app: 'python manage.py runserver'
- If the "Disallowed Host" page shows, copy & paste the cited HTTP Host & copoy into ALLOWED HOSTS in settings.py
- Try starting the app again



### Setup Environment Variables

#### Daisy's Instruction

#### Chat GPT (used in this instance)