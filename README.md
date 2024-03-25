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

## Configure your EC2 instance:
- Jenkins runs on port 8080, hence expose your instance to be accessed on port 8080
- picture
- Go to Security Group (NB: Ensure you verify the SG connected to the specific instance, if you have multiple instance running)
- Edit Inbound Traffic
- Add a new rule
- Save

## Configur Jenkins

Run the command to copy Jenkins admin password:

```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
copy password and loginto Jenkins:

- Picture

Install Plugins:

- Picture

Setup Admin User:

- Picture

Follow the prompt and Yaa! Jenkis id set for use:

- Picture

## Docker Slave Configuration

Instal DOcker with the following command:

```
sudo apt install docker.io
```

## Grant Both Jenkins user and Ubuntu user, permission to docker deamon with the command.

```
sudo su -
usermod -aG docker jenkins
usermod -aG docker ubuntu
systemctl restart docker
```

## Restart Jenkind
- http://<url>:port/restart

# Install Docker Plugins inside of Jenkins



- Set up jenkins pipeline to verify docker agent status
- picture

