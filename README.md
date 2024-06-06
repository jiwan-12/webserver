## Python environment setup guidelines
### Python3.7 or lastest stable version (eg: python3.12)
### django 5.0.4 or latest stable version (eg: Django==5.0.6)

### Strictly follow the python pep8 styling
     Recommanded: Use line length of 100 chars instead of 79
   #### VS code setup for the autopep8
     Install the VS code extension autopep8 and configure as the default formater
     Go to the extension settings(autopep8 extension) and add argument
      `--max-line-length=100`

### Recommanded packages list
      pylint # for liniting
      isort # to sort header
      autopep8 # for commandline fromating (optional)
      coverage # to see the test coverage
      
      To install above packages, add above list in the requirements.txt and run 
      `pip install -r requirements.txt`
    

### Pylint Setup
   #### If you are using pylint in a python virtual environment then please create pylint config file and add the following line to resolve import error
        To generate pylint config
            pylint --generate-rcfile > .pylintrc
         
        Update following line in .pylintrc
            init-hook='import sys; import os; sys.path.append("."); sys.path.append(os.path.abspath("src")); sys.path.append(os.path.abspath(<path-to-your-virtual-environment-site-packages>));'
            <path-to-your-virtual-environment-site-packages> eg: ../venv/lib64/python3.10/site-packages

*** Getting Started ***
    First clone the repository from Github and switch to the new directory:

    $ git clone git@github.com/USERNAME/{{ project_name }}.git
    $ cd {{ project_name }}

*** Activate the virtualenv for your project ***
    python3 -m venv cvenv
    source cvenv/bin/activate

*** Install project dependencies ***
    $ pip install -r requirements.txt

*** Apply the migrations ***
    $ python manage.py migrate

*** Run the development server ***
    $ python manage.py runserver