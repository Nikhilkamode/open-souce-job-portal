Configuration of Peeljobs
Create a directory using mkdir peeljobs, move to it using cd

mkdir peeljobs
cd peeljobs
Install virtualenv in your local using following command

sudo apt-get install virtualenv
Create an env in your project dir and activate using following.

virtualenv -p python3 env
source ../env/bin/activate
Again create another peeljobs directory for clonning the project.

mkdir peeljobs
cd peeljobs
Make sure git installed in your machine or else install by following below command.

sudo apt-get install git
git config --user.email <your email id>
git config --user.name  <your name>
Then intialize the git by using the following command

git init
Include peeljobs repository using following command.

git remote add origin https://github.com/MicroPyramid/opensource-job-portal.git
Pull the code of peeljobs using following command

git pull origin master
Install requirements, node and sass using following

sudo apt install curl
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get update
sudo apt install nodejs
npm install -g sass
pip install -r requirements.txt
We used postgressql here open shell and create the following database

sudo su - postgres
psql
create database peeldb;
We have to use third party related keys. We have to had those keys in order to run the application.

Sendgrid details

SG_USER=<sendgrid username>

SG_PWD=<sendgrid password>

Google developers account details

GOOGLE_CLIENT_ID=<oauth0 client id>

GOOGLE_CLIENT_SECRET=<oauth0 client secret-key>

ENABLE_GOOGLE_LOGIN=<variable to configure google login in application>

Facebook details

FB_APP_ID = <facebook access key id>

FB_SECRET = <facebook access secret-key>

Aws account details

AWSBUCKETNAME = <aws bucket name>

AWS_ACCESS_KEY_ID = <aws access key id>

AWS_SECRET_ACCESS_KEY = <aws access secret-key>

Git account details

GIT_APP_ID = <git api id>

GIT_APP_SECRET = <git secret-key>

LinkedIn account details

LN_API_KEY = <linkedin api id>

LN_SECRET_KEY = <linkedin secret-key>

Apply migrations to database using the following command

python manage.py migrate
Now run application using following command, and visit http://localhost:8000

python manage.py runserver
We’re using celery for sending emails, other related tasks in the application. Run celery using the following commands

celery -A peeljobs worker -l info

celery -A peeljobs beat -l info
