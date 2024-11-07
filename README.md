# FINAL IP <K8s>
setting the project ID

`gcloud config set project devopsk8s-441011`





# IP

## Overview
This project demonstrates the use of Vagrant and Ansible to set up a development environment. It includes instructions for creating a Vagrant file, launching the environment, testing Ansible playbooks, and accessing the project from the host machine.

## Table of Contents
- [Creating Vagrant File](#creating-vagrant-file)
- [Vagrant Up Command](#vagrant-up-command)
- [Testing Ansible Playbook Locally](#testing-ansible-playbook-locally)
- [Command to Launch Playbook](#command-to-launch-playbook)
- [Accessing the Project in the Host Machine](#accessing-the-project-in-the-host-machine)
- [Contributing](#contributing)
- [License](#license)

## Creating Vagrant File
To create the Vagrant file, follow these steps:

1. Open your terminal.
2. Navigate to your project directory.
3. Run `vagrant init`
4. specify the OS Image you want to pull

```

Vagrant.configure("2") do |config|
   config.vm.box = "geerlingguy/ubuntu2004"


end
```


## Vagrant Up Command
After creating the Vagrant file, run the following command to start your Vagrant environment:

```bash
vagrant up
```
![alt text](./static/Screenshot%20from%202024-11-03%2023-06-32.png)
Testing Ansible Playbook Locally
Once your Vagrant environment is up and running, you can test your Ansible playbook locally by accessing http://localhost:8080/ in the browser

## Destroying the VM

```
vagrant Destroy
```

![alt text](./static/Screenshot%20from%202024-11-03%2023-09-55.png)

## Command to Launch Playbook
To launch your Ansible playbook in the host machine, use the following command:

```
sudo ansible-playbook -i hosts.ini playbook.yml
```

## Accessing the Project in the Host Machine
After successfully running your playbook, you can access the project in your host machine. Here’s a snapshot of accessing the project.

![alt text](./static/Screenshot%20from%202024-11-03%2023-08-15.png)