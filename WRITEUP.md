
# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

--------------------
#### Analysis

**Costs**:
- An App service will be more flexible in terms of cost since more than one app can be made to share the App Service plan. <br>
- The Advantage with Virtual machine is that it can be deallocated when not in use in order to cut costs <br>

**Scalability**:
- Both the Virtual machine and the App Service can be scalled horizontally and vertically. VMs can be scalled horizontally using a VMSS, while App Service's have native Auto scalling properties <br>
- We can deploy multiple apps in App Service but in one VM Server we can only deploy one app. <br>

**Availability**:
- In terms of availability Virtual machines generally have more availability than App Services as it can run simultaneously at 2 regions at a time and hence making it available 99.95% whereas in App service, it depends on whether we have multiple instances activated or not and also if they are in different regions. <br>
- The only issue in VM is that it requires extra setup and configuration while running simulataneously at different regions to be fault tolerant and avoid downtimes during maintenance and upgrades <br>

**Workflow**:

- VM is a IaaS and hence the developer needs to set up most of the things like runtimes, compilers, firewalls ,etc whereas App Service is a Paas and so the developer just needs to create the app and rest all the things will be provided. <br>
- So it is fairly easier to deploy applications to App Service than it is to Virtual Machines. To resolve this issue an automated CI/CD pipeline could be designed but overhead time would be spent in the process <br>
    
--------------------
#### Decision

Deployment option: **App Service** <br>
Link for the deployed Article CMS app : ([https://article-cms.azurewebsites.net/](https://article-cms.azurewebsites.net/))

--------------------
#### Justification

- An App Service is a PaaS offering meaning that one just have to deploy their code and not worry about the underlying infrastructure. <br>
- The application is designed to be cloud native removing the need for server management and optimization.<br>
- It also has good pricing tiers and gives adequate room for scalability. Another caveat is the wide range of deployment options available that can easily be integrated into a production workflow <br>

--------------------

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.*

- App Services are limited to 14 GB of Memory and 4 VCPUs So if the application were to be a high compute application then need to extend hardware requirements would call for a Virtual Machine. <br>
- VMs would be needed if custom monitoring and logging solutions is required. <br>
- Also, if the application has dependencies to specific softwares on a server then a VM would be more suitable. <br>
