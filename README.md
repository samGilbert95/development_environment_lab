# Vagrant Install ReadMe

---
### Introduction
This readme is intended to be a walkthrough which will allow the user to learn the necessary commands to create and run the code in this repo inside a virtual machine.

#### Requirements
In order to run the vagrant file, you must have the following installed:

* Virtual Box
* Vagrant

If you do not have either of these installed, please follow the links provided.

* Virtual Box: https://www.virtualbox.org/wiki/Downloads
* Vagrant: https://www.vagrantup.com/docs/installation/

##Setting up Vagrant


#### Step 1: Setup VM
Call vagrant init + the name of the VM box you wish to use

---
#### Step 2: Create VM
Call vagrant up.

```
vagrant up
```

 This creates the VM based on the specifications given in the vagrant file.

---
#### Step 3 : Access VM
Call vagrant ssh.

```
vagrant ssh
```

This will enable you access to the ubuntu command line on the virtual console.

---
#### Step 4 : Update/ Upgrade
Call

```
sudo apt-get update && upgrade
```

This should install the most up to date version of the VM.

---
#### Step 5 : Install Server
Call
 
```
sudo apt-get install nginx -y
```
 This will install nginx, which will host the localserver. -y will automatically answer all prompts with yes.

---
##Connecting to the site

To check that the server is running, enter 

```
curl http://localhost
```

If working, this will show the site in html form within your console.

In order to display the program within a browser, you will need to enter the ip address. To find the IP address, enter 

```
ifconfig
```

This should show you the IP. Enter this into your browser to display the server.

---

## Editing IP
To edit your ip address, enter your VagrantFile and add this line underneath the config.vm.box command

```
config.vm.network "private_network", ip: "192.168.10.100"
```

Once this change has been made, you will need to reload your terminal. To do this run

```
vagrant exit
vagrant reload
```