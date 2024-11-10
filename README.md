# IP(4)
----------------------------------------------------------------
## Website URL
- **Site URL:** [http://34.35.49.118/](http://34.35.49.118/)


### Setting the Google Cloud Project ID
```bash
gcloud config set project devopsk8s-441011
```

### Confirming GCP Configuration
To check your current GCP configuration:
```bash
gcloud config list
```

 ![GCP Configuration](./static/Screenshot%20from%202024-11-10%2008-13-08.png)

---

### Creating a GKE Cluster
To create a GKE cluster, use the following command:
```bash
gcloud container clusters create devopsk8scluster --region africa-south1-a --project devopsk8s-441011
```

 ![Cluster Creation](./static/Screenshot%20from%202024-11-10%2008-34-15.png)

The cluster is now created, as visible in the Cloud Dashboard.

 ![Cluster in Dashboard](./static/Screenshot%20from%202024-11-10%2008-53-41.png)

---

### Installing the Auth Plugin
To install the required auth plugin for GKE, run the following:
```bash
sudo apt-get install google-cloud-sdk-gke-gcloud-auth-plugin1
```

### Applying Kubernetes Files
To apply all files in the `k8s` folder:
```bash
kubectl apply -f k8s/
```

 ![Apply Kubernetes Files](./static/Screenshot%20from%202024-11-10%2008-47-48.png)

After applying, the nodes will be visible in the Kubernetes dashboard.

 ![Nodes in Dashboard](./static/Screenshot%20from%202024-11-10%2008-55-22.png)

---

### Pod Status After Deployment
After applying the files, the pods are visible in the dashboard. However, the backend pod failed to deploy.

 ![Pod Status](./static/Screenshot%20from%202024-11-10%2008-58-35.png)

To check the status of all pods:
```bash
kubectl get pods
```

 ![Pod Status in Terminal](./static/Screenshot%20from%202024-11-10%2009-22-52.png)

---

### Terminal Setup Structure
 ![Terminal Setup](./static/Screenshot%20from%202024-11-10%2018-34-41.png)

---

### Website with Added Item
 ![Item Added](./static/Screenshot%20from%202024-11-10%2018-35-33.png)


# IP 3

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