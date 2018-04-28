# Setup a LAMP environment in Vagrant

LAMP stands for: Linux (OS/Kernel), Apache (Web Server), MySQL (Database), PHP (Scripting Language).
It is an open-source Web development environment which lets you create web applications. 

Vagrant is a piece of software through which you can create and configure virtual development environments.
It is an highly efficient tool for managing virtual machines via CLI. This increases your and your team's productivity and flexibility.


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

### Prerequisites

Download & install the latest version of Vagrant & Virtual Box,
by visiting Vagrant website and VirtualBox website. 

Download the following shell script on your server or clone it with the following command.

### Installing

Let us now setup LAMP development environment in Vagrant with below steps:

#1- Create a directory where we would be creating the instance:

mkdir -p ~Study/LAMP Script/lamp

cd ~Study/LAMP Script/lamp

git clone https://github.com/peleduri/LAMP-in-Vagrant.git #Give the execution right to it. 

chmod +x script.sh


#2- Now we are required to initialize the Vagrant box. #This initializes the current directory to be a Vagrant environment by creating an initial Vagrantfile if one does not already exist. #If a first argument is given, it will prepopulate the config.vm.box setting in the created Vagrantfile. #If a second argument is given, it will prepopulate the config.vm.box_url setting in the created Vagrantfile.

vagrant init

#3 This will create a VagrantFile. Edit the VagrantFile as listed in VagrantFile.

#4- Let us now start provisioning the LAMP installation. #For that, create a simple shell script named script.sh using your favorite text editor as listed in script.sh.

#5- After saving the script.sh, run: #This command creates and configures guest machines according to your Vagrantfile.

vagrant up

#It will do lot of things. You would be able to see as what it is doing on the stdout. #To give you an overview, it will start with importing the debian/jessie64 base box, then it will SSH into the box, then it will set the hostname of the machine(we have specified this in the Vagrantfile), then it start updating and installing the LAMP stack. #Please note- While installing mysql-server, it will set it's root password to 'rootpass' since we have mentioned this in the script.sh file.


## Running the tests

#6- Now after the vagrant is done with installation, you are ready to go. SSH into the vagrant box as:

vagrant ssh lamp

#7- Verify the installations by:

dpkg -l | grep "apache2|mysql-server-5.5|php5"

#You'll see all these packages listed and this means they have been installed successfully. With this you're done with setting up the LAMP development environment in Vagrant :)


## Built With

* howtoforge (https://www.howtoforge.com/tutorial/ubuntu-vagrant-install-and-getting-started/) - HowtoForge provides user-friendly Linux tutorials.
