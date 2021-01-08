# L4-Load-balancing-in-Azure-for-IaaS
we will be using Standard load balancer not L7 load balancer (Application gateway)

Load Balancing plan for IaaS with L4 Standard Load balancer.

We will pursue with Scale set instead of using typical VM’S. Some key benefits of the Scale set is below:

•	Azure virtual machine scale sets provide the management capabilities for applications that run across many VMs, automatic scaling of resources, and load balancing of traffic. Scale sets provide the following key benefits:
•	easy to create and manage multiple VMs
•	When you have many VMs that run your application, it's important to maintain a consistent configuration across your environment. For reliable performance of your application, the VM size, disk configuration, and application installs should match across all VMs.
•	With scale sets, all VM instances are created from the same base OS image and configuration. This approach lets you easily manage hundreds of VMs without additional configuration tasks or network management.
•	Scale sets support the use of the Azure load balancer for basic layer-4 traffic distribution.
•	Provides high availability and application resiliency
•	Scale sets are used to run multiple instances of your application. If one of these VM instances has a problem, customers continue to access your application through one of the other VM instances with minimal interruption.
•	For additional availability, you can use Availability Zones to automatically distribute VM instances in a scale set within a single datacenter or across multiple datacenters.
•	Allows application to automatically scale as resource demand changes.

Current Scateset setup for xx-servers.

![image](https://user-images.githubusercontent.com/58148717/104039183-a9791e80-519b-11eb-8dd5-da61d9fa838a.png)

we have 2 instances 

![image](https://user-images.githubusercontent.com/58148717/104039233-ba299480-519b-11eb-87f6-2d8c9b6056b7.png)

since we already our Scaleset up and running now we will we create the New standard load balancer for xx-servers and our scale set will be using Load balancer’s public IP in order to distribute the traffic. Load Balancer distributes inbound flows that arrive at the load balancer's front end to backend pool instances. These flows are according to configured load balancing rules and health probes Below is the example of Load balancer.

![image](https://user-images.githubusercontent.com/58148717/104039693-505dba80-519c-11eb-8456-6d238cf66d81.png)

![image](https://user-images.githubusercontent.com/58148717/104039966-ae8a9d80-519c-11eb-9241-253e9f8d134a.png)

After everything is in place, we will configure the DFS (Distributed file server) With the help of DFS all instances of our webservers will stay in SYNC 24/7

![image](https://user-images.githubusercontent.com/58148717/104040295-150fbb80-519d-11eb-9d50-b3861b61bae3.png)

Backend nodes are pointing to Azure SQL HyperScale
for more information: https://docs.microsoft.com/en-us/azure/azure-sql/database/service-tier-hyperscale

Complete Architecture along with Virtual machine scaleset, Load balancing and Azure SQL 

![image](https://user-images.githubusercontent.com/58148717/104040995-f65df480-519d-11eb-908f-0c8e8a6639fa.png)


























