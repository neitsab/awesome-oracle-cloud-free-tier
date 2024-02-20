# Awesome Oracle Cloud Free Tier

> A (WIP) curated list of awesome resources to make the best out of [Oracle Cloud Free Tier](https://www.oracle.com/cloud/free/).

*"[Oracle Cloud Infrastructure](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/baremetalintro.htm) (OCI) is a set of complementary cloud services that enable you to build and run a range of applications and services in a highly available hosted environment."*

> [!TIP]
> This list is laid out in a "knowledge progressive" order, from not knowing anything about OCI to making one's first steps on the platform, all the way to more advanced use cases.

## Official documentation

### Free tier

* [Oracle Cloud Infrastructure Free Tier](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm) and [Always Free Resources](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm) detail the services available in the offer
* Limits:
    * [Reclamation of Idle Compute Instances](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm#compute__idleinstances) describes the qualifying thresholds and what happens if compute instances are deemed idle
    * [Official OS selection](https://docs.oracle.com/en-us/iaas/Content/Compute/References/images.htm) is limited to Oracle Enterprise Linux, CentOS and Ubuntu
    * [Outgoing SMTP blocked by default on port 25](https://docs.oracle.com/en-us/iaas/releasenotes/changes/f7e95770-9844-43db-916c-6ccbaf2cfe24/)
        * [Workarounds](#workarounds) to those limits are detailed below

### First steps

* [Getting Started with Oracle Cloud Free Tier](https://www.youtube.com/watch?v=VVyNhlsc8Yk) (YouTube 2023-02) walks us through the signup process
* [Learn About Oracle Cloud Basics](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/concepts.htm#conceptstest2) is **_strongly recommended_** to learn more about _tenancy_, _compartment_, _OCID_, _Availability Domains_ etc., as those concepts will keep coming up whenever you want to do something
    * then explore topics of interest in the [reference guide](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/baremetalintro.htm), such as [Get to know the Console](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/console.htm)

### Compute instances

* [Launching Your First Linux Instance](https://docs.oracle.com/en-us/iaas/Content/GSG/Reference/overviewworkflow.htm) is a portal to the relevant docs for each step of the process
* [Free Tier: Install WordPress on an Ubuntu Instance](https://docs.oracle.com/en-us/iaas/developer-tutorials/tutorials/wp-on-ubuntu/01-summary.htm) is a practical and integrated tutorial for the previous workflow; it also illustrates how to add an ingress rule to allow incoming traffic on port 80

### Networking

* [Create and configure a virtual cloud network](https://docs.oracle.com/en/learn/lab_virtual_network/index.html) combines text, video and hands-on lab to learn about VCNs
* [Enable IPv6 for Oracle Cloud Infrastructure](https://www.youtube.com/watch?v=yxm3Bn7uHyw) (YouTube, 2021-09) is helpful in configuring IPv6 connectivity

### First month tips

* Set up a [budget](https://docs.oracle.com/en-us/iaas/Content/Billing/Concepts/budgetsoverview.htm) as soon as you start so as to know which operations cost money and thus will not be available at the end of the trial period (unless you upgrade to a [#Pay As You Go](#pay-as-you-go) account); see also [Checking Your Expenses and Usage](https://docs.oracle.com/en-us/iaas/Content/Billing/Concepts/costs.htm)
* it can be smart to use the free credits to do operations that won't be possible at the end of the trial period, such as [bringing your own image](https://docs.oracle.com/en-us/iaas/Content/Compute/References/bringyourownimage.htm) and then using one of the 5 free volume backups to image a base install before removing the custom image
* [When Your Trial Period Ends](https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm#freetrial__when-trial-ends) details what happens at the end of the first month depending on what sort of resources you are using; to summarize: anything that is beyond what the Always Free tier offers will get instantly terminated, unless you upgrade to a [#Pay As You Go](#pay-as-you-go) account.

## Community guides, tutorials and HOWTOs

### Articles

* [Oracle Cloud - Setting up a Server on the "Always Free" Tier](https://ryanharrison.co.uk/2023/01/28/oracle-cloud-free-server.html) (2023-01) covers signup, instance creation and login into the VM with many screenshots
* [Build Your Own Free VPN with Oracle Cloud](https://thoughtrealm.medium.com/build-your-own-free-vpn-with-oracle-cloud-d6455f882cb0) (2022-09) covers setting up a Wireguard VPN using [PiVPN](https://www.pivpn.io/), with any screenshots as well; notable for covering VCN creation and Security List adjustments
* [Oracle Free Tier VPS - Best Practices](https://blog.johnswitzerland.com/oracle-free-tier-tailscale/) (2023-01) gives good tips such as setting up a password for your instance user account, enabling Tailscale to SSH, backing up...

### YouTube playlists

* [Oracle Free Tier Tutorials](https://www.youtube.com/playlist?list=PLSk3zfDlC1f_Up6GBgckMIqLdS_HRjdEy) covers many combinations and possibilities such as Remote Linux Desktop, NextCloud, OpenVPN, WordPress, HestiaCP, Nginx, email...
* [Oracle Cloud Ubuntu Instance Guide](https://www.youtube.com/playlist?list=PLFVkn-yha3ECaFgz-Y3qVhcyGahLM4puc) has a different focus with many security-related projects (PiHole, proxys, VPN) but also log servers, containers, Minecraft, Jitsi...

## Projects

* [Cloudblock](https://github.com/chadgeary/cloudblock/): deploys Wireguard VPN, Pi-Hole DNS Ad-blocking and DNS-over-HTTPS in a cloud provider using Terraform and Ansible

### Kubernetes

* [Learn About Provisioning an ARM Kubernetes Cluster on OCI and Deploying an Nginx Website](https://docs.oracle.com/en/solutions/build-arm-kubernetes-cluster-oci/index.html): short tutorial hosted by Oracle; its second part uses a Terraform script available on GitHub to provision an cluster with Always Free resources
* [Kubernetes on Oracle Cloud...for free](https://me.mattscott.cloud/kubernetes-on-oracle-cloud-for-free/) (2023-08): converting an account to [#Pay As You Go](#pay-as-you-go) so as to use Oracle Kubernetes Engine (OKE) to easily set up a cluster while still using only free resources
* [k3s-fcos-oci](https://github.com/m5lapp/k3s-fcos-oci): create a four-node K3s cluster running Fedora CoreOS as the node OS using Always Free resources

## Workarounds

### OS selection

#### Netboot.xyz

* [netboot.xyz](https://netboot.xyz) lets you boot various operating system installers or utilities from a single tool over the network.
    * [The Ultimate Debian Installation Guide for Oracle Cloud | Free Tiers Account Step-by-Step](https://youtu.be/R3SIvTv3TBg) (YouTube 2023-07) demonstrates the whole process

#### Arch

* [How to install Arch Linux ARM on an Oracle Cloud Free Tier VPS](https://reddit.com/r/archlinux/comments/14iqb6h/how_to_install_arch_on_an_oracle_cloud_free_tier/) (Reddit 2023-06)
* [Replace Oracle Cloud Linux with Arch Linux ARM remotely](https://gist.github.com/zengxinhui/01afb43b8d663a4232a42ee9858be45e) (GitHub Gist)
* [Install Arch Linux  (x86_64) on Oracle Cloud Free Tier](https://gist.github.com/amishmm/e2dc93e65cf79116f2ef2d542f05e61b) (GitHub Gists)

#### Debian

* [DIY install debian on Oracle Cloud Infrastructure ( Free Tier ) - ARM64](https://gist.github.com/4abhinavjain/893ec13c651bee08088c8f4661998952) (GitHub Gist)
* [Oracle Free Tier: Install Debian on the x86 micro instances with full disk encryption](https://pieterhollander.nl/post/oracle-free-tier-debian-install-amd64/)
* [Debian Network Reinstall Script](https://github.com/bohanyang/deb)

### Pay As You Go

[Pay As You Go](https://docs.oracle.com/en/cloud/get-started/subscriptions-cloud/ocpib/frequently-asked-questions.html) (often referred to as "PAYG") is as its name implies, a type of account where you get charged for what you use.

It unlocks all paid features and services beyond Always Free ones, but that doesn't mean you have to use them: you can keep using only Always Free resources) while benefiting from the avantages of an upgraded account.

* **Pros:** access to all services & functionalities (including Oracle Kubernetes Engine), no risk of idle compute instance reclamation, upgrade to standard support level (which allows to ask the unblocking of outgoing SMTP traffic on port 25 etc.)
* **Cons:** may incur charges if resources beyond those available in the Always Free tier are consumed

This is why if you want to upgrade to a Pay As You Go account while still only using Always Free resources, it is strongly recommended to **set up a budget with the lowest possible threshold** ($0.01) and to enable notifications whenever you cross it: this will help mitigate any undesired spending (see [#First month](#first-month)).
