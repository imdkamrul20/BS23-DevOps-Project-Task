In this project the goal is to install kubernetes cluster using vagrant and configuration management tool ansible.

Create an Ansible playbook for Kubernetes master

Create a directory named kubernetes-setup in the same directory as the Vagrantfile. 

Create two files named master-node-ansible-playbook.yml and worker-node-ansible-playbook.yml in the directory kubernetes-setup.

Create the Ansible playbook for Kubernetes node

Go to the directory Task-2/ and then run "vagrant up"

 1 master 2 worker node kubernetes cluster will be installed. Now we will install kubernetes dashboard and metric server. 

Dashboard Installaion

kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.3.1/aio/deploy/recommended.yaml

kubectl apply -f admin-role-binding.yml
kubectl apply -f dashboard-adminuser.yml


Metric server installation*

This install all the necessary kubernetes objects for metric server. Now create some pods and wait for sometime to load the metric server. 
wget -O v0.3.6.tar.gz https://codeload.github.com/kubernetes-sigs/metrics-server/tar.gz/v0.3.6
tar -xzf v0.3.6.tar.gz
kubectl apply -f metrics-server-0.3.6/deploy/1.8+/

