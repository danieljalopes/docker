# References
# https://www.jenkins.io/doc/book/installing/#debian-ubuntu

FROM ubuntu:20.04

ARG APT_KEY_DONT_WARN_ON_DANGEROUS_USAGE=1

#update and install minimal tools
RUN apt-get update \
  && apt-get install apt-utils --yes \
  && apt-get install gnupg2 --yes \
  && apt-get --yes install  wget \
  && apt-get --yes install openjdk-8-jdk 

# get and install jenkins lts
RUN wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | apt-key add - \
  && echo "deb http://pkg.jenkins.io/debian-stable binary/" > /etc/apt/sources.list.d/jenkins.list \
  && apt-get update \
  && apt-get --yes install jenkins \
  && service jenkins start \
  && echo "Initial Admin Password" \
  && cat /var/lib/jenkins/secrets/initialAdminPassword
  

# get and install jenkins weekly build
#RUN wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | apt-key add - \
#  && echo "deb https://pkg.jenkins.io/debian binary/" > /etc/apt/sources.list.d/jenkins.list \
#  && apt-get update \
#  && apt-get install jenkins


EXPOSE 8080

CMD ["/bin/bash"]


