# GWBJIra
docker run -d -p 5431:5432 --name superset-jirabidb josephgeorgek/gwbreportdb:latest
docker run -d -p 8180:8088 --name superset-jirabi josephgeorgek/gwbreportapp:latest

docker exec -it superset-jirabi superset fab create-admin \
               --username admin \
               --firstname Superset \
               --lastname Admin \
               --email admin@superset.com \
               --password admin


docker exec -it superset-jirabi superset db upgrade


//docker exec -it superset-jirabi superset load_examples

docker exec -it superset-jirabi superset init


postgresql://192.168.64.4:XXXXXXXXXX@db/university-session1
53

DATABASE_URL=postgres://{user}:{password}@{hostname}:{port}/{database-name}
DATABASE_URL=postgres://postgres:postgres@192.168.64.4:5431/university-session1

superset load_examples: Initialized instance data, connection error, because the instance data on github cannot be obtained

Go to github to download the data file: https://github.com/apache-superset/examples-data

Unzip the file and map it to the local apache server

Modify examples/helpers.py base_url to the local address

computed coliumns
CLOSEDSP
(case when "Status" like 'DONE' then  "Custom field _Story Points_" when "Status" like 'PROD' then  "Custom field _Story Points_" when "Status" like 'SIT' then  "Custom field _Story Points_" when "Status" like 'UAT' then  "Custom field _Story Points_" else 0 end )





yum install -y python3-devel.x86_64
sudo yum upgrade python-setuptools
sudo yum install gcc gcc-c++ libffi-devel python-devel python-pip python-wheel openssl-devel cyrus-sasl-devel openldap-devel
//pip download apache-superset
pip install apache-superset --no-index --find-links=/.


superset db upgrade
superset fab create-admin

# Load some data to play with
#superset load_examples

# Create default roles and permissions
superset init

# To start a development web server on port 8088, use -p to bind to another port
superset run -p 8088 --with-threads --reload --debugger
