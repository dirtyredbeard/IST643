# Data Center Operations with VMware vSphere <!-- omit in toc -->

> Estimated Completion Time: 8-10 Hours
>
> Due Date: You should have an understanding of these concepts by the start of class next week.

## Learning Objective <!-- omit in toc -->

To garner a deeper understanding of the services, processes, and conceptual understanding required to effectively manage a VMware vSphere based software defined data center (SDDC). These exercises are also intended to sharpen your basic systems administration knowledge.

In doing these walkthroughs you will:

- Explore VMware vSphere 6.7
- Explore vRealize Operations Manager
- Explore vSphere Log Insight
- Understand storage management with vSAN
- Utilize PowerCLI to automate vSphere tasks
- Understand vSphere clustering, high availability, and distributed resource scheduling

## Table of Contents <!-- omit in toc -->

- [Walkthroughs](#walkthroughs)
  - [Accessing the Hands on Labs](#accessing-the-hands-on-labs)
  - [VMware vSphere Automation - PowerCLI](#vmware-vsphere-automation---powercli)
  - [vSAN v6.7](#vsan-v67)
  - [Clustering Deep Dive](#clustering-deep-dive)
  - [New features and Update Manager](#new-features-and-update-manager)
- [Questions](#questions)

## Walkthroughs

It is very difficult to get a test vSphere software defined data center (SDDC) to learn on. Luckily VMware provides hands on labs, which are guided tours of features and administrative tasks needed to operate a SDDC. Below I have sourced a number of hands on labs (HOL) and specific sections which are particularly important to understanding the day-to-day management of a data center using VMware products.

Explore beyond the documentation! These are fully setup vSphere environments which you have administrative access to!

> Note:
>
> I have not added information about network management with NSX --since you've gone through that before.
>
> If you need a refresher I recommend checking out "HOL-1903-01-NET - VMware NSX Data Center for vSphere".

### Accessing the Hands on Labs

Login or register for a free account with [VMware Hands On Labs Online](https://labs.hol.vmware.com) to access these walk throughs.

### VMware vSphere Automation - PowerCLI

One of the most efficient ways to learn a new system is to experiment with its API's\Libraries. In this lab you will build out a data center, clusters, deploy VM's, set high availability priorities, and manage VM taks. All core concepts one needs to understand if setting up or maintaining a SDDC.

Once logged into the HOL portal, search for 'HOL-1911-05-SDC - VMware vSphere Automation - PowerCLI' to access the lab.

### vSAN v6.7

Now that you have learned to automate basic tasks within a data center, let's dive in a bit deeper to the storage layer that ties clusters and data centers together. This lab does a great job encapsulating the true day-to-day administrative tasks associated with managing enterprise storage --there is one section about setting up vSAN, and then  multiple about setting up policies, monitoring and health checks to ensure the storage is performant, trustworthy, and fault tolerant.

Within the HOL portal, search for 'HOL-1908-01-HCI - VSAN V6.7' to access the lab.

### Clustering Deep Dive

Now that you understand how to automate and manipulate hosts, resources, and virtual machines through PowerCLI as well as understanding the storage layer which virtual machines and clusters utilize. Let's get a deeper understanding of the 'software defined' part of the SDDC.

I know that you have experienced NSX in another course, so you understand networks in a SDDC. However, how does the SDDC leverage these dynamic virtual networks and virtual shared storage to solve business problems? High availability (HA) and Distributed Resource Scheduling (DRS)!

The ultimate goal is to deploy a VM to a cluster, and then let the cluster manage performance and uptime going forward...but how? VMware explains it very well in this talk: [vSphere Clustering Deep Dive](https://www.youtube.com/watch?v=beqAIHSbkfc)

### New features and Update Manager

It is always a good idea to understand the new features of any technology you are learning or utilizing.

I recommend you step through this HOL "HOL-1911-01-SDC - What's New in VMware vSphere 6.7".

Particularly the section 'Getting started with Update Manager' (Page 50). Understanding the patching process for a VMware SDDC is very important --one wouldn't want to have unpatched vulnerabilities on the machines they host their business applications on!

## Questions

After completing these walkthroughs you should be able to answer the following questions:

1. What is a baseline and how would an administrator leverage it?
2. What is a snapshot and what are the two types of snapshots?
3. What is a resource pool?
4. What is a heartbeat?
5. In regards to storage with vSAN, what metrics does VMware allow you to monitor?