# local_db

Creates a containerized postgres database with dummy data

### Steps

##### Postgres Container
Install docker desktop https://docs.docker.com/desktop/

Clone the repo and do the following:

- create the image + container 
```docker compose up -d```

- create a bash session on the container 
```docker exec -i local_db bash``` 

- log into the database using credentials in `./database.env`
```psql -d database -U user -W```

- verify that the table contains data from my_table.csv
```
select * from public.my_table;
```
```
    a     |    b     |    c
----------+----------+----------
 column a | column b | column c
 column a | column b | column c
 column a | column b | column c
 column a | column b | column c
(4 rows)
```

##### Python Container
To install virtual env locally
```
pip install pyenv
pip install pipnev
pyenv install 3.7.3
pyenv local 3.7.3
pyenv shell 3.7.3
pipenv shell
pipenv install
```

To use the python container
```
docker exec -it local_db_py bash
python
```
