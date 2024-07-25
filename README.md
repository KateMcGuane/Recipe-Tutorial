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
- Navigate to project directyory; Command 'virtualenv venv'


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
- 'pip install django'