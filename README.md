# dockerfiles
This repo contains dockerfiles to set up Jenkins and slaves on centos 7

Build the images from the dockerfiles located in the directories.

Run the docker image to start Jenkins master as :

docker run -u root -p 80:8080 -d --restart=always -v /var/run/docker.sock:/var/run/docker.sock  --volumes-from jenkins-datavolume --name jenkins-master-2.8 -e USER='jenkins' jenkins:version1.0

I have used a data volume container (optional). You can create the data volume container as :

docker create -v /var/jenkins_home --name jenkins-datavolume jenkins
