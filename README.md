README.md

=========proper infrastacture deployment solution==========

To design and achieve highly available microservice deployment solution we have keep in mind below points

- Continuous Planning
- Continuous Development
- Continuous Integration
- Continuous Testing
- Continuous Monitoring
- Continuous Feedback
- Continuous Delivery
- Continuous Deployment
- Continuous Operations

In this Readme i will demonastrate a proper deployment solution which will include

-Continuous integration and continuous delivery (CI/CD)
The code that passes automated tests is integrated in a single, shared repository on a server. Frequent code submissions prevent a so-called “integration hell” when the differences between individual code branches and the mainline code become so drastic over time that integration takes more than actual coding.

Continuous delivery, detailed in this article, is an approach that merges development, testing, and deployment operations into a streamlined process as it heavily relies on automation. This stage enables the automatic delivery of code updates into a production environment.

-Continuous deployment
At this stage, the code is deployed to run in production on a public server. Code must be deployed in a way that doesn’t affect already functioning features and can be available for a large number of users. Frequent deployment allows for a “fail fast” approach, meaning that the new features are tested and verified early. There are various automated tools that help engineers deploy a product increment. The most popular are Chef, Puppet, Azure Resource Manager, and Google Cloud Deployment Manager.

-Continuous monitoring
The final stage of the DevOps lifecycle is oriented to the assessment of the whole cycle. The goal of monitoring is detecting the problematic areas of a process and analyzing the feedback from the team and users to report existing inaccuracies and improve the product’s functioning.

-Infrastructure as a code
Infrastructure as a code (IaC) is an infrastructure management approach that makes continuous delivery and DevOps possible. It entails using scripts to automatically set the deployment environment (networks, virtual machines, etc.) to the needed configuration regardless of its initial state.

Without IaC, engineers would have to treat each target environment individually, which becomes a tedious task as you may have many different environments for development, testing, and production use.

-Containerization
Virtual machines emulate hardware behavior to share computing resources of a physical machine, which enables running multiple application environments or operating systems (Linux) on a single physical server or distributing an application across multiple physical machines.

Containers, on the other hand, are more lightweight and packaged with all runtime components (files, libraries, etc.) but they don’t include whole operating systems, only the minimum required resources. Containers are used within DevOps to instantly deploy applications across various environments and are well combined with the IaC approach described above. A container can be tested as a unit before deployment. Currently, Docker provides the most popular container toolset.

-Microservices
The microservice architectural approach entails building one application as a set of independent services that communicate with each other, but are configured individually. Building an application this way, you can isolate any arising problems ensuring that a failure in one service doesn’t break the rest of the application functions. With the high rate of deployment, microservices allow for keeping the whole system stable, while fixing the problems in isolation.

My thoughts and design plan

**Gitops & version control system: As this option i will choose Gitlab as a single point source of truth.Where all code can be pushed for infrastacture & base backend codes

**System os: As creating servers and maintaining server linux should give us better performence.

**Server configuration: To configure server Ansible i should prefer because it is agentless and more reliable for all kinds of linux distros.

**Platform: entire insfrusture we can host in trusted and reliable platform like AWS. to achieve high availibility ,fault tollerence ,
    scalabilty can be easily achieve through various service of aws.stateful application can be backed up in simple storage service  or in separate server's ebs as a snapshot 

**Conatainerization: Docker is the most powerful and renowed tools for acheiving microservice architecture hosting.

**Orchestration: kubernetes is widely used for managing docker containers.

**Application load balancer: service mesh can be used as loadbalancer for route the traffic accros the service containers which support ingress,proxy.

**Ci : As i am using git source of truth backend code can be build in gitlab as well with the help of gitlab runner.and builded images can stored easily in gitlab container registry with single ci file.

**Testing: Automated testing can done with the help of selenium running on a temporary container when the ci file will run, a single images can be used in every project to test with different test script written in python or bash. 

**Logging : Efk stack can be used for monitoring the service log and storing the log in single point.

**monitoring : There are some default metrics of kubernetes by which we can monitor the cluster health and visualize them with Grafana

**Cd: Flux is a good tool that can be intregated with git and deploy the code into the environment.

**infra monitoring: for fault tollerance and as a alert method nagios should used.By this tool we can monitor server health and network isuues.

As i want to keep the environment lightweight and developer friendly thats why put everything in single point.

