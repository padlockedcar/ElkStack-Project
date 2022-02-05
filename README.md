Deployed ELK Stack
------------------------------

The network indicated below was created using the files available in this repository.

<img width="813" alt="ElkStackDiagram" src="https://user-images.githubusercontent.com/81398383/139724075-464c4721-c7a7-46f0-86be-e832abf7bfc6.png"> 


#### This document contains the following details:
- Topology
- Access Policies
- Configuration
  - Beats in Use
  - Monitored Machines
- Ansible Build How-to


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

A load-balanced instance offers an application that will be highly available, while restricting access to the network.
- *Load balancers insure the availability of servers and services*

- *A jumpbox acts as a gateway to private servers, adding to our security and privacy.*

Utilizing an ELK server aids in monitoring VMs for changes.
- *Filebeat*
- *Metricbeat*

The configuration details of each machine may be found below.

| Name    | Function            | IP Address | Operating System |
|:--------|:-------------------:|:----------:|:----------------:|
| Jumpbox | Gateway             | 10.0.0.5   | Linux (Ubuntu)   |
| DVWA 1  | Webserver           | 10.0.0.11  | Linux (Ubuntu)   |
| DVWA 2  | Webserver           | 10.0.0.6   | Linux (Ubuntu)   |
| DVWA 3  | Webserver           | 10.0.0.12  | Linux (Ubuntu)   |
| ELK     | Elasticsearch Stack | 10.1.0.4   | Linux (Ubuntu)   |

### Access Policies

The internal machines can’t be accessed from the public Internet.
Only the jumpbox machine can accept connections from the Internet.
Machines within the network can only be accessed by the jumpbox.
- *jumpbox*
    - *Public IP: 40.121.163.19*
    - *Private IP: 10.0.0.5*


Summary of access policies:

| Name          | Publicly Accessible                           | Allowed IP Address          |
|:-------------:|:---------------------------------------------:|:---------------------------:|
| Jumpbox       | Yes- Port 22 (SSH)                            | ***.***.**.***              |
| DVWA 1,2,3    | No                                            | Load Balancer- * |
| Load Balancer | Yes- Port 80 (HTTP)                           | *                           |
| ELK           | Yes- Port 5601 (Kibana), Port 9200 (HTTP API) | 10.0.0.0/16                 |

### Elk Configuration

The ELK Machine used Ansible to automate configuration. 

The playbook triggers the below:
- *Install docker*
- *Install python3-pip module*
- *Install docker module for pip3*
- *Increase/Use more memory*
- *Download and launch ELK container*

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- *10.0.0.6*
- *10.0.0.11*
- *10.0.0.12*

Following Beats installed:
- *Filebeat and Metricbeat on DVWA 1,2, and 3*

These Beats collect data from each machine:
- *Filebeat collects log data.*
- *Metricbeat collects data from system usage.*

