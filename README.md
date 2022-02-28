## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Network Diagram](/Images/diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook files may be used to install only certain pieces of it, such as Filebeat.

  -https://github.com/CheyneTaylor/ELK-stack-project/tree/main/Playbooks

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- Load balancers are used to distribute traffic in the system to help prevent DDoS attacks.
- A Jumpbox gives control to userfrom a single point which can be monitored and secured.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system metrics.
- Filebeats watches for changes to them system and forwards the data to centralized location
- Metricbeats records data from specified servers

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump-Box-Povisioner | Gateway  | 10.1.0.5   | Linux(unbuntu20.04)            |
| Web-3     | Server         | 10.1.0.17           | Linux(ubuntu 18.04)                 |
| Web-5    |  Server        |  10.1.0.18          |         Linux(ubuntu 18.04)         |
| ELK-1     | ELK Server         | 10.0.0.4           |         Linux(ubuntu 18.04)         |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 73.166.150.134

Machines within the network can only be accessed by Jump-Box-Provivisioner.
- My Personal computer through port 5601 is the only machine which can access the ELK server
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump-Box-Provisiner | Yes              | 73.166.150.134   |
|   Web-5       |      No               |        10.1.0.5              |
|   Web-3       |     No                |                 10.1.0.5     |
| ELK-1 | Yes | 73.166.150.134:5601 |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Automating the configuration is helpful because you can insure consistency in installation and configuration
The playbook implements the following tasks:
- doanloads docker.io and python3.pip
- installs docker
- increases virtual memory
- doawnloads and deploys ELK container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Udate the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-3 : 10.1.0.17
- Web-5 :10.1.0.18
We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeats monitors log files
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
