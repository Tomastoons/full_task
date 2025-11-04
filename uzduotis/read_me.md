# for this task I was using UBUNTU OS

## instructions how to run


## double-check Python 3 installation:

python3 --version

## If Python 3 is already installed on your machine, this command will return the current version of Python 3 installation. In case it is not installed, for UBUNTU OS, you can run the following command and get the Python 3 installation:

sudo apt install python3

##to run this task solution, We will use PostgreSQL as our relational database. To interact with PostgreSQL database, you need to install the libpq-dev using the following command in UBUNTU OS:

sudo apt install libpq-dev

## in different OS just install PostgreSQL and then create database as described bellow

## now you need to activate isolated environment by running, to deactivate read instruction in bottom of the file:

conda activate uzd2_env

## now create local database in your localMachine:

CREATE DATABASE payloads;
CREATE ROLE superuser WITH PASSWORD 'slapta';
GRANT ALL PRIVILEGES ON DATABASE payloads TO superuser;
ALTER ROLE "superuser" WITH LOGIN;


## and now run server by this command:

uvicorn main:app --host 0.0.0.0 --port 8000


## endpoints usage example: 

## POST:

http://127.0.0.1:8000/event

{
	"event_type":"message",
	"event_payload":"hello sir!"
}

## GET:

http://127.0.0.1:8000/event  


## if you will want to deactivate conda environment in the end of the session:

conda deactivate
