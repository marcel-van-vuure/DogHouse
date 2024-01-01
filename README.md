# Building the application
mvn clean install

# running the application
java -jar target/quarkus-app/quarkus-run.jar

you can use yaml file: dogs.yaml and import it for example in postman and issue your commands from there.
The yaml file will give you more information about what response codes to expect for each api

alternativaly you can use curl commands like the ones below to call the api:

# crud examples to send to the app:
# get all dogs
curl -X GET -i http://localhost:8080/dogs -H "Accept: application/json"

# get dogs by name
curl -X GET -i http://localhost:8080/dogs/by-name/Aurelie -H "Accept: application/json"

#create a dog
curl -X POST -i http://localhost:8080/dogs -H "Content-Type:application/json" -d '{"name":"Rocky","dateOfBirth":"2023-10-04","sex":"Male"}'

#update a dog
curl -X PUT \
  -i http://localhost:8080/dogs/1 \
  -H 'Content-Type: application/json' \
  -d '{
    "dateOfBirth": "1980-10-04",
    "sex": "Male",
    "name": "Rocky"
  }'

#delete a dog
curl -X DELETE \
  -i http://localhost:8080/dogs/3


#get a dog by id
curl -X GET -i http://localhost:8080/dogs/1 -H "Accept: application/json"

