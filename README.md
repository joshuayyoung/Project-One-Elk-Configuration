## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Update the path with the name of your diagram]: \Project One- Networking and Confiuration\Project Details\Images\Network Diagram(1)

![image](https://github.com/joshuayyoung/Project-One-Elk-Configuration/blob/main/diagram/Network%20Diargram%20(1).jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.
		
[filebeat-playbook](ansible/filebeat.yml.txt)
    		
[install-playbook](ansible/install-elk.yml.txt)

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
What aspect of security do load balancers protect? What is the advantage of a jump box? 
-A jump box protects the availablity of the netowrk and also restricts access to the network from unknown public source.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
What does Filebeat watch for? 
-Filebeat watches for changes in system traffic and changes to logs in the network.
What does Metricbeat record?
-Metricbeat gives updates on the statisitics and metrics of the network.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Fucntion | IP Address              | Operating System |

| Jump-Box | Gateway  | 10.0.0.4                | Linux         |

| Web-1    | server   | 10.0.0.5                | Linux          |

| Web-2    | server   | 10.0.0.6                | Linux          |

| Web-3    | server   | 10.0.0.7                | Linux         |

| Elk      | Monitor  | private ip: 10.1.0.4/  public ip: 20.98.105.52    | Linux          |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Add whitelisted IP addresses:
- 72.82.55.236 (local computer)
- 10.0.0.5 (Web-1)             
- 10.0.0.6 (Web-2)              
- 10.0.0.7 (Web-3)
- private: 10.1.0.4 | public: 20.98.105.52 (Elk)

Machines within the network can only be accessed by ssh.
 Which machine did you allow to access your ELK VM? What was its IP address?
 -The machine that has access to the ELK vm is the Jump-Box; its Public IP Address is 40.88.14.28 and it's Private IP Address is 10.0.0.4 .

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |
|          |                     |                      |
|          |                     |                      | 
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible?
- When you automate a task in ansible, you are able to put that task into multiple servers across your from one playbook instead of having to edit/add tasks to those severs manually.

The playbook implements the following tasks:
n 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- install.docker.io
- install: python3-pip
- install: docker
- command: sysctl -w vm.max_map_count=262144

-The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- List the IP addresses of the machines you are monitoring:
- 10.0.0.5 (Web-1)             
- 10.0.0.6 (Web-2)              
- 10.0.0.7 (Web-3)

We have installed the following Beats on these machines:
- Specify which Beats you successfully installed:
- I was able to successfully install Filebeat

These Beats allow us to collect the following information from each machine:
- In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
- Filebeat collects the changes done to our system logs and traffic; Metricbeat collects stats and metrics, such as ping CPU usage, In/OutBound Traffic, Disk space used, and Memory Usage of the web servers.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

Answer the following questions to fill in the blanks:_
- Which file is the playbook? Where do you copy it?
- 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?
 
