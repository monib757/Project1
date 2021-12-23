# Project1# 

## Automated ELK Stack Deployment


The files in this repository were used to configure the network depicted below.

[![Cloud Diagram](https://github.com/monib757/Project1/blob/main/Diagrams/Azure%20Virtual%20Network.jpeg "Cloud Diagram")](https://github.com/monib757/Project1/blob/main/Diagrams/Azure%20Virtual%20Network.jpeg "Cloud Diagram")



These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the configuration file may be used to install only certain pieces of it, such as Filebeat.

  
[Filebeat Playbook](httphttps://github.com/monib757/Project1/blob/main/Ansible/Filebeat-playbook.yml:// "Filebeat Playbook")
[Elk Config](htthttps://github.com/monib757/Project1/blob/main/Ansible/Elk_config.ymlp:// "Elk Config")
[Metricbeat Playbook](https://github.com/monib757/Project1/blob/main/Ansible/Metricbeat-playbook.ymlhttp:// "Metricbeat Playbook")
[Pentest Yml](htthttps://github.com/monib757/Project1/blob/main/Ansible/Pentest.ymlp:// "Pentest Yml")
[Ansible Config](httphttps://github.com/monib757/Project1/blob/main/Ansible/ansible.cfg:// "Ansible Config")
[Host](hthttps://github.com/monib757/Project1/blob/main/Ansible/hoststp:// "Host")

This document contains the following details:

- Description of the Topologu
- Access Policies
- ELK Configuration
- Beats in Use
- Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
What aspect of security do load balancers protect? What is the advantage of a jump box?_The load balances protects against DOS attacks having multiple servers running the same website.  The jump box is used to hardened security and limiting access to the rest of the network only allowing traffic from authorized ips. Elk gives us the capability to monitor traffic for vulnerabilities.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
-What does Filebeat watch for? 
Filebeat monitors logs and location of data you specify
-What does Metricbeat record?
The metrics such as uptime and statistics that it collects and ships them to the output specified.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web 1    | Web Ser  | 10.0.0.5   | Linux            |
| Web 2    | Web Ser  | 10.0.0.6   | Linux            |
| ELK      | Monitor  | 10.2.0.4   |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 
168.61.146.135

Machines within the network can only be accessed by Jump Box VM.
TODO: Which machine did you allow to access your ELK VM? What was its IP address?
The jump box ip is 168.61.146.135

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 168.61.146.135       |
| Web-1    | No                  | 10.0.0.5             |
| Web-2    | No                  | 10.0.0.6             |
  Elk      | No                    10.2.0.4
  
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because services running can b
-What is the main advantage of automating configuration with Ansible? The main advantage of automation is that it saves time and allows you the capability to focus on other important tasks.

The playbook implements the following tasks:

- install docker.io
- install python3-pip
- docker
- increase memory to 262144
- launch the elk container
**The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance**.

[[![Docker ps](https://github.com/monib757/Project1/blob/main/Images/Elk%20docker%20ps.jpg "Docker ps")](hthttps://github.com/monib757/Project1/blob/main/Images/Elk%20docker%20ps.jpgtp:// "Docker ps")[)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-List the IP addresses of the machines you are monitoring

Web-1 10.0.0.5 
Web-2 10.0.0.6

We have installed the following Beats on these machines:
Specify which Beats you successfully installed
Metricbeat and Filebeat
These Beats allow us to collect the following information from each machine:
Filebeats monitors suspicious logfiles or locations that’s specified.  
Metricbeat measures the usage of system resources that can be collected and monitored to include uptime.



### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to ansible
- Update the host file to include elk and webserver
- Run the playbook, and navigate to kibana to check that the installation worked as expected.


-Which file is the playbook? Where do you copy it?
The ansible.cfg file to /etc/ansible
-Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
The host file. Specify the ip addresses so that ansible which knows which machine.

Which URL do you navigate to in order to check that the ELK server is running? http://elk public ip/app/Kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc
