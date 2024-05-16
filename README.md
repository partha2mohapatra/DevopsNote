# Setup Jenkins on Linux(UBUNTU)

## Install Jenkins in Linux
  sudo apt-get update

## Install Java 17
  sudo apt install openjdk-17-jdk openjdk-17-jre -y


## Set JAVA_HOME Variable
    cd /usr/lib/jvm/java-17-openjdk-amd64
    
    export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
    
    echo $JAVA_HOME
    
    export PATH=$PATH:$JAVA_HOME/bin
  
- To set it permanently, open environment file in vi editor
- sudo vi /etc/environment
- write this in file at the end -> JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64

## Jenkins Installation
  Add Jenkins Repository key to the system, it will add key in the apt-key package.
  - curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  - echo 'deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/' | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
  - sudo apt-get update && sudo apt-get install jenkins -y

    
## Start the Jenkins service:
  sudo systemctl start jenkins

## Enable Jenkins on startup:
  sudo systemctl enable jenkins

## Check Jenkins status:
  systemctl status jenkins

## Copy Jenkins Admin Password
  sudo cat /var/lib/jenkins/secrets/initialAdminPassword

###############################################################

# Setup NGROK Proxy

## Install NGROK Proxy in linux
     curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok
  
## Sign up to NGROK proxy and verify email

## Add auth token
    ngrok config add-authtoken <token>

## Link to Jenkins
- ngrok http http://122.11.11.11:8080

- ![image](https://github.com/partha2mohapatra/DevopsNote/assets/111627485/024ac915-7870-45bf-bbfe-9d4c24cef65e)

## Go to Github repo Setings> Webhook
- Add the payload url(copy from ngrok proxy terminal)
    https://d924-20-90-114-254.ngrok-free.app/github-webhook/




