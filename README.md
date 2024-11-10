# FINAL IP <K8s>

## my site is at http://34.35.49.118/

## backend endpoints http://34.35.57.91:5000/api/products

setting the project ID

`gcloud config set project devopsk8s-441011`


Frontend and Backend: These will typically use Deployment objects since they are stateless.
Database: If your database requires persistent storage, you can use a StatefulSet to ensure each pod gets a unique, stable identity and its own persistent storage. This can be achieved with PersistentVolume and PersistentVolumeClaim.

# confirming GCP configs
`gcloud config list`

<!-- ![alt text](<Screenshot from 2024-11-10 08-13-08.png>) -->

![alt text](./static/Screenshot%20from%202024-11-10%2008-13-08.png)

# creating GKE cluster
`gcloud container clusters create [CLUSTER_NAME] --region [REGION] --project [PROJECT_ID]`

`
gcloud container clusters create devopsk8scluster --region africa-south1-a --project devopsk8s-441011
`
![alt text](./static/Screenshot%20from%202024-11-10%2008-34-15.png)

### cluster credted in the cloud dashboard

![alt text](./static/Screenshot%20from%202024-11-10%2008-53-41.png)



## installing auth-plugin1

`sudo apt-get install google-cloud-sdk-gke-gcloud-auth-plugin1`

## applying all files in the k8s folder
`kubectl apply -f k8s/`
![alt text](./static/Screenshot%20from%202024-11-10%2008-47-48.png)
### Nodes visible in dashboard

![alt text](./static/Screenshot%20from%202024-11-10%2008-55-22.png)







### pods visible in dashboard after appling them
Pod status, the backend pod failed to deploy
![alt text](./static/Screenshot%20from%202024-11-10%2008-58-35.png)




### status of pods
`kubectl  get pods`
![alt text](<Screenshot from 2024-11-10 09-22-52.png>)





## terminal setup structre
![alt text](<Screenshot from 2024-11-10 18-34-41.png>)


## site with an item added
![alt text](./static/Screenshot%20from%202024-11-10%2018-35-33.png)



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