- To install Jenkins, I firstly created a security group on AWS that allows SSH on port 22 and custom TCP on port 8080. 
- I then created an instance attached to this security group. 
- I SSH'ed into the instance and to install jenkins and the java it needs to work, I ran; 
```
sudo apt-get update

sudo apt install openjdk-11-jre -y

java -version

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins -y

sudo systemctl enable jenkins

sudo systemctl start jenkins

sudo systemctl status jenkins
```
- After which I entered the public IP address of my instance :8080 [x.xx.xxx.x:8080] into my browser to find my Jenkins sign in dashboard. 
