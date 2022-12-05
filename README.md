# EasyPharma
Pharma store Management : web application which helps in managing pharmacy stores.

Steps to execute the prject:
Download the project zip file.

we need to install following softwares to execute the projetc packages:

      python 3 - you can download the latest version of python from https://www.python.org/downloads/
  
      django -2.1.7 can use pip install Django==2.1.7 from cmd to install django

run following command from terminal to launch server :

      > python manage.py runserver

Any code changes to models should be migrated :
      
      > python manage.py makemigrations
      >python manage.py migrate

Any changes to static files must also be recorded by running following command :

      > python manage.py collectstatic noinput
      
