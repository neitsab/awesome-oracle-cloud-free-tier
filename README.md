# Awesome Oracle Cloud Free Tier

> A (WIP) curated list of awesome resources to make the best out of [Oracle Cloud Free Tier](https://www.oracle.com/cloud/free/).

*"[Oracle Cloud Infrastructure](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/baremetalintro.htm) (OCI) is a set of complementary cloud services that enable you to build and run a range of applications and services in a highly available hosted environment."*

> [!TIP]
> This list is laid out in order to bring readers from not knowing anything about OCI, to discovering its Free Tier and the platform, signing up, making their first steps by creating an instance, all the way to giving pointers to create a Kubernetes cluster made up of only Always Free resources.

## Official documentation
### Free tier

* [Oracle Cloud Infrastructure Free Tier](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm) and [Always Free Resources](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm) detail the services available in the offer
* Limits:
    * [Reclamation of Idle Compute Instances](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm#compute__idleinstances) describes the qualifying thresholds and what happens if compute instances are deemed idle
    * [Platform Images](https://docs.oracle.com/en-us/iaas/Content/Compute/References/images.htm) are restricted to Oracle Enterprise Linux, CentOS and Ubuntu
    * See below for [workarounds](#workarounds) to both of those limits

### First steps

* [Getting Started with Oracle Cloud Free Tier](https://www.youtube.com/watch?v=VVyNhlsc8Yk) (YouTube 2023-02) walks us through the signup process
* [Learn About Oracle Cloud Basics](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/concepts.htm#conceptstest2) is **_strongly recommended_** to learn more about _tenancy_, _compartment_, _OCID_, _Availability Domains_ etc., as those concepts will keep coming up whenever you want to do something
    * then explore topics of interest in the [reference guide](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/baremetalintro.htm), such as the [Get to know the Console](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/console.htm)

### Compute instances

* [Launching Your First Linux Instance](https://docs.oracle.com/en-us/iaas/Content/GSG/Reference/overviewworkflow.htm) is a portal to the relevant docs for each step of the process
* [Free Tier: Install WordPress on an Ubuntu Instance](https://docs.oracle.com/en-us/iaas/developer-tutorials/tutorials/wp-on-ubuntu/01-summary.htm) is a practical and integrated tutorial for the previous workflow; it also illustrates how to add an ingress rule to allow incoming traffic on port 80

### Networking

* [Create and configure a virtual cloud network](https://docs.oracle.com/en/learn/lab_virtual_network/index.html) combines text, video and hands-on lab to learn about VCNs
* [Enable IPv6 for Oracle Cloud Infrastructure](https://www.youtube.com/watch?v=yxm3Bn7uHyw) (YouTube, 2021-09) is helpful in configuring IPv6 connectivity
### First month tips

* It is a good idea to set up a [budget](https://docs.oracle.com/en-us/iaas/Content/Billing/Concepts/budgetsoverview.htm) as soon as you start, so as to know which operations cost money and thus will not be available at the end of the trial period (unless you upgrade to a [#Pay As You Go](#pay-as-you-go) account); see also [Checking Your Expenses and Usage](https://docs.oracle.com/en-us/iaas/Content/Billing/Concepts/costs.htm)
* it can be smart to use the free credits to do operations that won't be possible at the end of the trial period, such as 
* [When Your Trial Period Ends](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm#freetrial__when-trial-ends) details what happens at the end of the first month depending on what sort of resources you are using; to summarize: anything that is beyond what the Always Free tier offers will get instantly terminated, unless you upgrade to a [#Pay As You Go](#pay-as-you-go) account.

## Community guides, tutorials and HOWTOs

### Articles

* [Oracle Cloud - Setting up a Server on the "Always Free" Tier](https://ryanharrison.co.uk/2023/01/28/oracle-cloud-free-server.html) (2023-01) covers signup, instance creation and login into the VM with many screenshots
* [Build Your Own Free VPN with Oracle Cloud](https://thoughtrealm.medium.com/build-your-own-free-vpn-with-oracle-cloud-d6455f882cb0) (2022-09) covers setting up a Wireguard VPN using [PiVPN](https://www.pivpn.io/), with any screenshots as well; notable for covering VCN creation and Security List adjustments

### Video

* [Oracle Free Tier Tutorials](https://www.youtube.com/playlist?list=PLSk3zfDlC1f_Up6GBgckMIqLdS_HRjdEy) (playlist) covers many combinations and possibilities such as Remote Linux Desktop, NextCloud, OpenVPN, WordPress, HestiaCP, Nginx, email...
* [Oracle Cloud Ubuntu Instance Guide](https://www.youtube.com/playlist?list=PLFVkn-yha3ECaFgz-Y3qVhcyGahLM4puc) (playlist) has a different focus with many security-related projects (PiHole, proxys, VPN) but also log servers, containers, Minecraft, Jitsi...

## Projects

* [Cloudblock](https://github.com/chadgeary/cloudblock/): deploy a new official pihole-docker + linuxserver.io's docker-wireguard + docker-cloudflared (for DoH) on any major cloud provider with Terraform, or deploy on an existing (Ubuntu-based) server using Ansible.

### Kubernetes cluster

#TODO

## Workarounds

### OS selection

#TODO

### Pay As You Go

[Pay As You Go](https://docs.oracle.com/en/cloud/get-started/subscriptions-cloud/ocpib/frequently-asked-questions.html) (sometimes referred to as "PAYG") is as its name implies, a type of account where you get charged for what you use and _only_ for what you use: the account in itself does not cost anything (_i.e._ it is not a subscription), and if you don't use any paid services then you aren't charged anything.

It unlocks all paid features and services beyond Always Free ones, but that doesn't mean you _have to use_ them: you can keep using only Always Free resources (see [this thread](https://news.ycombinator.com/item?id=35159404) on Hacker News).

* **Pros:** no risk of idle compute instance reclamation, upgrade to standard support level
* **Cons:** may incur charges if resources beyond those available in the Always Free tier are consumed

This is why if you want to upgrade to a Pay As You Go account while still only using Always Free resources, it is strongly recommended to **set up a budget with the lowest possible threshold** ($0.01) and to enable notifications whenever you cross it: this will help mitigate any undesired spending (see [#First month](#first-month)).

