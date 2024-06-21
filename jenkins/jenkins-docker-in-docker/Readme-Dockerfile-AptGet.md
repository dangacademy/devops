docker build -t df-jenkins-dind-apt -f ./DockerfileDindWithApt .

docker run \
  --name jenkins-dind-apt \
  --restart=on-failure \
  -e TZ=Asia/Kolkata \
  --detach \
  --privileged \
  -u root \
  --publish 1212:8080 \
  --publish 50000:50000 \
  --volume jenkins_home:/var/jenkins_home \
  --volume jenkins-docker-certs:/certs/client:ro \
  --volume /var/run/docker.sock:/var/run/docker.sock \
  df-jenkins-dind-apt
