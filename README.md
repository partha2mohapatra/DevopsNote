# DevopsNote

*Install Jenkins in Linux
- sudo apt-get update

*Install Java 17
- sudo apt install openjdk-17-jdk openjdk-17-jre -y


*Set JAVA_HOME Variable
cd /usr/lib/jvm/java-17-openjdk-amd64
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
echo $JAVA_HOME
export PATH=$PATH:$JAVA_HOME/bin

set it permanently, open environment file in vi editor
