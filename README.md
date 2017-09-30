# Using VM-Series Firewalls to Secure Internet-Facing Web Workloads

![VM Series Firewall](https://raw.githubusercontent.com/fullscale180/PAN/master/archdiagram.png "VM Series Firewall")


Use this ARM template to deploy: 

* An outbound VM-Series firewall which includes two VM-Series firewalls behind an internal load balancer to handle outbound internet traffic. 
The outbound load balancer receives traffic from multiple backend application servers and distrubutes it to the VM-Series firewalls.  The 
firewalls enforce security policies to protect your workloads and send the allowed traffic out to the internet. 

* One or more application gatways which include two VM-Series firewalls between a pair of Azure load balancers. The external load balancer
is an Azure Application Gateway (a web load balancer) that also serves as the Internet facing gateway, which  receives traffic and distributes 
it to the VM-Series firewalls. The firewalls enforce security policies to protect your workloads, and send the allowed traffic to the internal 
load balancer which is an Azure Load Balancer (Layer 4) that load balances across a pair of sample Apache web servers. 

As demand for your web services increase, you can add more web servers and deploy additional VM-Series firewalls for more capacity. Each tier, the VM-Series firewalls and web servers, are deployed in separate Availability Sets for higher availability and redundancy against planned and unplanned outages. Refer to Azure documentation for more information on [Availability Sets] (https://docs.microsoft.com/en-us/azure/virtual-machines/virtual-machines-linux-manage-availability). A sample configuration file for VM-Series firewall is also included. After you import this configuration file, be sure to (a) customize the security policies to your needs and (b) <b>set a custom password</b> for the firewall instead of the value in the sample file. Refer to the documentation for steps on how to import the sample configuration file. 

**Support Policy**
 
This CFT is released under an as-is, best effort, support policy. These scripts should be seen as community supported and Palo Alto Networks will contribute our expertise as and when possible. We do not provide technical support or help in using or troubleshooting the components of the project through our normal support options such as Palo Alto Networks support teams, or ASC (Authorized Support Centers) partners and backline support options. The underlying product used (the VM-Series firewall) by the scripts or templates are still supported, but the support is only for the product functionality and not for help in deploying or using the template or script itself. Unless explicitly tagged, all projects or work posted in our GitHub repository (at https://github.com/PaloAltoNetworks) or sites other than our official Downloads page on https://support.paloaltonetworks.com are provided under the best effort policy.
 
**Documentation**
* Release Notes: Included in this repository.
* Technical Documentation:[VM-Series Deployment Guide] (https://www.paloaltonetworks.com/documentation/71/virtualization/virtualization/set-up-the-vm-series-firewall-in-azure/deploy-the-vm-series-and-azure-application-gateway-template.html)
* About the [VM-Series Firewall for Azure] (https://azure.paloaltonetworks.com)

***Deploy outbound VM-Series Firewall with HA Ports on an internal Azure Load Balancer Standard***

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjigarshah04%2FPAN%2Fmaster%2FazureDeployInfra.json)

***Deploy a sample Application with separate inbound firewall and backend***

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjigarshah04%2FPAN%2Fmaster%2FazureDeployApp.json)

