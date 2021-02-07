## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

!(Images/Cloud-Diagram2.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? Load balancers protect applications through traffic compression, caching and ssl offload. What is the advantage of a junp box? Jump box is a highly secure method of having security professionals access one hub (virtual machine) before launching any administrative tasks. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the application and system servers.
- _TODO: What does Filebeat watch for? Filebeat watches for logs and log events.
- _TODO: What does Metricbeat record? Metricbeat records metricset data modules that contain logic and instructions. 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  |104.211.1.4   Linux        
| Arlington            52.249.56.166 Linux
| Web--1               104.41.135.92 Linux
| Web--2               104.41.135.92 Linux
| web--3               104.41.135.92 Linux

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 10.0.0.9
- 10.0.0.8
- 10.0.0.7
- 10.1.0.4

Machines within the network can only be accessed by the jumpbox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?
Arlington VM
public: 52.249.56.166
private: 10.1.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 96.255.147.167       |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because there are many configurations.
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Configure elk vm with docker container using the remote user access, azdmin
- Install docker, python3-pip
- Configuration includes systemd module to allow for more memory to run elk
-Elk will run on the following ports: 5601, 9200, and 5044

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: (Images/kibana.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: public (52.249.56.166)
         private (10.1.0.4)

We have installed the following Beats on these machines:
- _TODO: filebeat

These Beats allow us to collect the following information from each machine:
- _TODO: Filebeats collects log files in order to monitor and deliver log events. 


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-config.yml file to Alrington web VM.
- Update the _____ file to include...
- Run the playbook, and navigate to filebeat installation module status to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? filebeat-playbook.yml file copied to /etc/ansible/roles
- _Which file do you update to make Ansible run the playbook on a specific machine? install-elk.yml file to update. How do I specify which machine to install the ELK server on versus which to install Filebeat on? Add ip address to configuration file. 
- _Which URL do you navigate to in order to check that the ELK server is running? 52.249.56.166:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._