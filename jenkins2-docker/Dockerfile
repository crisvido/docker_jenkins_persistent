FROM jenkins/jenkins:lts
USER root

# Install missing libraries
RUN apt-get update
RUN apt-get install libxss1 -y
RUN apt-get install libx11-xcb1 
RUN apt-get install -y -q xvfb libgtk2.0-0 libxtst6 libxss1 libgconf-2-4 libnss3 libasound2


# Install Chrome
RUN wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
RUN dpkg -i google-chrome-stable_current_amd64.deb; apt-get -fy install

RUN mkdir /var/log/jenkins
RUN mkdir /var/cache/jenkins
RUN chown -R jenkins:jenkins /var/log/jenkins
RUN chown -R jenkins:jenkins /var/cache/jenkins
USER jenkins
ENV JAVA_OPTS="-Xmx8192m"