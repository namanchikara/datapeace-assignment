![travis-ci status](https://travis-ci.com/namanchikara/datapeace-assignment.svg?branch=master)
# datapeace-assignment    
Assignment for Backend Dev. position at Data Peace AI Technologies. 


# Technologies used
* Flask
* Flask-sqlAlchemy
* MySQL
* json, (demo data from http://demo9197058.mockable.io/users)

# Alternate solution using `heroku` and `postgres`
* Checkout https://github.com/namanchikara/heroku-datapeace-assignment
* I've hosted it on heroku, you can checkout https://datapeace-assignment.herokuapp.com/api/users
* I have NOT tested it and hence I don't recommend it for use; However all end points seems to be working in it as well and codebase is much more elegant
* Test 11 in `test.py` seems to be failing for `heroku` version, That's why I would recommend you to checkout below given solution whoose db is `mySQL` rather than `postgre`
* Both of the solutions are using `SQLAlchemy ORM`. 

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
* Open `run_app.py` and change `password` to your mysql password you set in previous steps
* Now to run the application run command `python run_app.py`
* Server would now be running on `localhost` i.e `127.0.0.1`
* To run tests, run command `python test.py`


# Using Application.
* As this was a backend project, no GUI is present(Sorry), However you can use `postman` https://www.getpostman.com/ to send requests and receive response objects.
* I've covered most of the endpoints in `test.py` file

# End points
* `/api/test/multipleUsers` - `POST` - To add multiple users 
  1. Post request must send data in `json` format to populate db
  2. Response with HTTP status code `201` on success `{}`

* `/api/test/multipleUsers` - `DELETE` - To delete all users in db

* `/api/users` - `GET` - To list the users. 
  1. Response with HTTP status code `200` on success.
  2. Also, supports some query parameters:-
  3. `page` - a number for pagination
  4. `limit` - no. of items to be returned, default limit is 5
  5. `name` - search user by name as a substring in First Name or Last Name (Note, use substring matching algorithm/pattern to match the name)
  6. `Sort` - name of attribute, the items to be sorted. By default it returns items in ascending order if  this parameter exist, and if the value of parameter is prefixed with ‘-’ character, then it should return items in descending order.
  7. Sample query endpoint:- `/api/users?page=1&limit=10&name=James&sort=-age`. This endpoint should return list of 10 users whose first name or last name contains substring given name and sort the users by age in descending order of page 1.

* `/api/users` - `POST` - To create a new user
  1. Request Payload should be like in json format :-
  2. Response with HTTP status code `201` on success and `{}`
  3. This endpoint will create a new user inside the database

* `/api/users/{id}` - `GET` - To get the details of a user
  1. Here `{id}` will be the id of the user in path parameter 
  2. Response with HTTP status code `200` on success
  3. Sample query looks like:- `/api/users/1` of `GET` type

* `/api/users/{id}` - `PUT` - To update the details of a user
  1. Here `{id}` will be the id of the user in path parameter 
  2. Request Payload should be like in `json` format for updating first name, last name and age:-
  3. Response with HTTP status code `200` on success and `{}`

* `/api/users/{id}` - `DELETE` - To delete the user
  1. Here {id} will be the id of the user in path parameter 
  2. Response with HTTP status code `200` on success `{}`




Build is currently passing on travis, for futher information regarding build or debugging installation process visit https://travis-ci.com/namanchikara/datapeace-assignment
