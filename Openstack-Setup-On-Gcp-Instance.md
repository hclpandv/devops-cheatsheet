## How to install Openstack Devstack with Heat test server on a Google Cloud Platform's Instance

1. We have to build a gcp instance to start with.  
2. Please choose `Ubuntu 16.04 LTS` image to build the instance as this linux flavor is tested most as per openstack documentation.Make sure your enable the external IP and http traffic allowed settings during instance build process.  
3. Once the Instance is ready and running, Login using ssh through gcp cloud console and type below commands to install and setup apche server and a static website to test whether external IP is producting a test webpage through your browser.

```
sudo apt-get update && sudo apt-get install apache2 -y
echo '<!doctype html><html><body><h1>Hello World!</h1></body></html>' | sudo tee /var/www/html/index.html
```
4. use the external IP of your instance to test whether 'Hello World' is loaded into your browser example: http://35.229.115.255/ 

#### Installing the openstack devstack (Openstack Developement test environment)

##### Add Stack User
Devstack should be run as a non-root user with sudo enabled (standard logins to cloud images such as “ubuntu” or “cloud-user” are usually fine).  

You can quickly create a separate stack user to run DevStack with below commands:

```
$ sudo useradd -s /bin/bash -d /opt/stack -m stack
```
Since this user will be making many changes to your system, it should have sudo privileges:

```
$ echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack
$ sudo su - stack
```
##### Download DevStack

```
$ git clone https://git.openstack.org/openstack-dev/devstack
$ cd devstack
```
The devstack repo contains a script that installs OpenStack and templates for configuration files

Create a local.conf
```
vi local.conf
```
Create a local.conf file with 4 passwords preset and Heat plugin info at the root of the devstack git repo.

```
[[local|localrc]]
ADMIN_PASSWORD=secret
DATABASE_PASSWORD=$ADMIN_PASSWORD
RABBIT_PASSWORD=$ADMIN_PASSWORD
SERVICE_PASSWORD=$ADMIN_PASSWORD

#Enable heat services
enable_service h-eng h-api h-api-cfn h-api-cw

#Enable heat plugin
enable_plugin heat https://git.openstack.org/openstack/heat

#Automatically download and register a VM image that heat can launch.
IMAGE_URL_SITE="http://download.fedoraproject.org"
IMAGE_URL_PATH="/pub/fedora/linux/releases/25/CloudImages/x86_64/images/"
IMAGE_URL_FILE="Fedora-Cloud-Base-25-1.3.x86_64.qcow2"
IMAGE_URLS+=","$IMAGE_URL_SITE$IMAGE_URL_PATH$IMAGE_URL_FILE
```

This is the minimum required config to get started with DevStack.  

Start the install
```
./stack.sh
```
This will take a 15 - 20 minutes, largely depending on the speed of your internet connection. Many git trees and packages will be installed during this process.

