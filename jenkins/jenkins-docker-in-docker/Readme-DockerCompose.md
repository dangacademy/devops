# In case of update in docker image release and don't want to use cache
# docker-compose build --no-cache --pull

# In case container is already created using docker command
docker container rm dc-jenkins-dind-shell

# If any change is done in dockerfile keep changes to minimum
docker-compose build

# In case any changes done in compose file
docker-compose up -d

