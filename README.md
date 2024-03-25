# Jenkins Master Node Setup

This project highlights Jenkins as a robust Continuous Integration tool and its pivotal role in delivering software solutions efficiently.

## STEPS
- Setup and Configure EC2 instance
- Install Jenkins
- Setup Jenkins
- Install and configure Docker Agent

# EC2 Instance Setup
- Go to your AWS console, sign in and launch an EC2 instance with ubuntu OS
- NB: Ensure to save a copy of your instance key
- With the public url of the running instance and the instance key
- log into your ec2 instance via a cli tool, to programmatically access your server.
-pitures

## Best Practise

Before proceeding with installations on your new EC2 machine, run the following command:
1.) Update system

```
sudo apt update
sudo apt upgrade (optional)
```

# Installing Jenkins

Pre-requisites: 
- Java (JDK)

Consult the java documentation if installing in a differet Operating System.

## Run the following commands to install jenkins

2.) Install Java:

```
sudo apt install openjdk-11-jre
```

Verify Java is installed properly:

```
java -version
```

3.) Install Jenkins with the following command:

```
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
