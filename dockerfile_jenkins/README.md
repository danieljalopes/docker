Build image
docker build -t "jenkins:myimg" .

Run Container
docker run -p 8080:8080 -it --name=jenkins_1 jenkins:myimg