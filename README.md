![travis-ci status](https://travis-ci.com/namanchikara/datapeace-assignment.svg?branch=master)
# datapeace-assignment    
Assignment for Backend Dev. position at Data Peace AI Technologies. 


# Technologies used
* Flask
* Flask-sqlAlchemy
* MySQL
* json, (demo data from http://demo9197058.mockable.io/users)

# Installation

* Install `python 3` and `git`
* Install `mysql-client` and `mysql-server`
* In terminal run `sudo mysql -e "use mysql; update user set authentication_string=PASSWORD('YOUR-PASSWORD-HERE') where User='root'; update user set plugin='mysql_native_password';FLUSH PRIVILEGES;create database datapeace; use datapeace;"` replace `YOUR-PASSWORD-HERE` with your desired `mysql` password
* In last step we set password for mySQL AND created a new database namded `datapeace` <- on which db operations will be performed in this application.
* Run `sudo mysql_upgrade -u root --password=YOUR-PASSWORD-HERE & sudo service mysql restart`
* Clone this repo by running command `git clone https://github.com/namanchikara/datapeace-assignment.git`
* Change directory to folder using `cd datapeace-assignment`
* In case you want to use virtualenv, then you can do that too, make sure `virtualenv` is installed and then run `virtualenv  venv -p python3` now to activate this virtual environment run `source venv/bin/activate`
* Run command `pip install -r requirements.txt`
* Now to run the application run command `python run_app.py`
* Server would now be running on `localhost` i.e `127.0.0.1`
* To run tests, run command `python test.py`


# Using Application.
* As this was a backend project, no GUI is present(Sorry), However you can use `postman` https://www.getpostman.com/ to send requests
* I've most of the endpoints in `test.py` file

Build is currently passing on travis, for futher information regarding build or debugging installation process visit https://travis-ci.com/namanchikara/datapeace-assignment.svg?branch=master
