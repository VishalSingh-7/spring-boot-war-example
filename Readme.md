# Spring Boot Hello World Example Project.

- check is user a root user.
- apt-get update
- apt-get install maven
- mvn test
- mvn package
- apt-get install tomcat9
- cp -rvf target/hello-world-0.0.1-SNAPSHOT.war /var/lib/tomcat9/webapps/app.war


#### How to install Tomcat Server
- To Download the Tomcat9 Server: https://tomcat.apache.org/download-90.cgi 
- Step to configure the tomcat server: https://phoenixnap.com/kb/install-tomcat-ubuntu

#### How to Install Jenkins
```sh
#!/bin/bash
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins -y
sudo apt-get update
sudo apt install fontconfig openjdk-21-jre -y
sleep 180
sudo systemctl start jenkins
sleep 180
sudo systemctl enable jenkins
```
