# devops_test

posgress credentials
--------------------

postgres \
madhupost

running postgress sql container
-----------------------------
sudo docker run --name my-postgres -e POSTGRES_PASSWORD=madhupost -d -p 5432:5432 postgres
 
 
 change the properties file
 ---------------------------
 
postgres.jdbc.url=jdbc:postgresql://privateip_of_aws_instance:5432/postgres \
postgres.jdbc.username=postgres \
postgres.jdbc.password=madhupost \

 
 Dockerfile
 ----------
FROM openjdk \
ADD . .  \
ENTRYPOINT java -DpropertyFileLocation=dbConnectionProperties.properties -jar dbConnectionCheck.jar


for building image
-------------------
docker build -t dbapp . \

running as a contianer
---------------------

docker run -d --name dbapp -p 9998:9998 dbapp \

both containers should be running \

access the app using ip:9998 \


