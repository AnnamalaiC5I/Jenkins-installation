# 1. Installing Jenkins

First, update the default Ubuntu packages lists for upgrades with the following command:
```bash
sudo apt-get update
```
Then, run the following command to install JDK 11:
```bash
sudo apt-get install openjdk-11-jdk
```
Now, we will install Jenkins itself. Issue the following four commands in sequence to initiate the installation from the Jenkins repository:
```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins
```
if the above curl and echo command doesn't work, get the updated keys from this link: https://www.jenkins.io/blog/2023/03/27/repository-signing-keys-changing/

Once that’s done, start the Jenkins service with the following command:
```bash
sudo systemctl start jenkins.service
```
To confirm its status, use:
```bash
sudo systemctl status jenkins
```
By default, Jenkins will run on port 8080.

To check the initial password, use the cat command as indicated below:
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

All Set! You can now start automating...

