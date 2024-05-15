# DevopsNote

- Install Jenkins in Linux
  sudo apt-get update

- Install Java 17
  sudo apt install openjdk-17-jdk openjdk-17-jre -y


- Set JAVA_HOME Variable
  cd /usr/lib/jvm/java-17-openjdk-amd64
  export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
  echo $JAVA_HOME
  export PATH=$PATH:$JAVA_HOME/bin
  (To set it permanently, open environment file in vi editor)
  sudo vi /etc/environment
  (write this in file at the end -> JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64)

- Jenkins Installation
  Add Jenkins Repository key to the system, it will add key in the apt-key package.
  curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  echo 'deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/' | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
  sudo apt-get update && sudo apt-get install jenkins -y

    
- Start the Jenkins service:
  sudo systemctl start jenkins

- Enable Jenkins on startup:
  sudo systemctl enable jenkins

- Check Jenkins status:
  systemctl status jenkins

- Copy Jenkins Admin Password
  sudo cat /var/lib/jenkins/secrets/initialAdminPassword


