# Stage 00 -- Introduction & Objectives
--------------------------------------------------------------------------------
# [RC1 Release Cycle Volunteer Project Board :D](https://github.com/containercraft/ocp-mini-stack/projects/1)
```
Currently under heavy development this ocp ministack has been functionally
tested extensively and is a mature v1 architecture design. 

RC1 Development Cycle architecture objectives can be seen in the design below. All
feature development for RC1 has been implimented in the project at this time and
barring extenuating circumstances we are in a feature freeze. Additional FRE
bugs are welcome and will immidiately be staged to RC2 development cycle 
objectives. 

Feature highlights of current gen design includes:
 - Completely self contained single host lab with multi host expandability options
 - Zero network or service configuration dependencies external to the host
 - Zero risk of dns/dhcp leakage onto external networks
 - Fully featured and normal network implimentation & behavior
 - Fully automated production like multi-node-cloud CoreOS provisioning (virtual guest nodes)
 - Ansible and Manual deploy methods are fully forkable and support release versioning

Current development status:
 - Manual setup method documentation is over 90% complete & functional
 - Infrastructure Docker Container images & deployment steps are 100% complete & Functional
 - All anticipated tasks & blockers now logged on RC1 project board as issues to be assigned
 - Ansible Development
   - Host Hypervisor Playbook 100% functional (see issue board for rc1 tasks)
   - VFW Gateway Playbook 90% functional - (see issue board for rc1 tasks)
   - CloudCtl Bastion Playbook ~25% functional - incomplete -
   - Infra Docker Container Playbook 0% complete, will be the most simple playbook

High Impact Fully POC Demonstrated RC2 Road Map Features:
 - Integrated ACME Lets Encrypt Certificate Automation
 - Domain Name Registration & DNS API automation (VIA GCP API)
 - Publicly publish services via overlay to low cost public cloud (EG: Digital Ocean Droplet)
 - Support for full stack build behind MAC Address controled ethernet (IE: corporate/hotel net)
 - Support for public service publishing via overlay over WWAN (Tested with Google Fi SIM)
 - WIFI only network access - IE: No hard wired ethernet connection (Tested with intel wifi module)

RC3 Final v1 Release Candidate Roadmap - Primary Objective:
 - Impliment entire stack on Red Hat official bits

v2 Release Roadmap:
 - Support VMWare Deployment
 - Support Disconnected Deployment
 - FRE Enable fully Deep Packet Inspection SSL MITM Proxied gateway (Disconnected & non)

v3 Release Roadmap:
 - Deploy via operator from minishift/CRC

Beyond v3:
 - Develop failure based success education & enablement curriculum
 - Develop "Deploy infrastructure via IaC" curriculum & Hands On DevOps Advocacy
 - Develop DevSecOps featureset to integrate SecOps as a practice
```
![CCIO_OCP MiniStack Lab_Diagram](zweb/drawio/rc1-design-goals/rc1-design-objectives.svg)

  + [01 Build Host]
  + [02 Build Bastion]
  + [03 Build Gateway]
  + [04 Setup_Dns]
  + [05 Setup HAProxy]
  + [06 Setup Dhcp]
  + [07 Setup Nginx]
  + [08 Setup Tftpd]
  + [09 Deploy Cloud]
  + [10 Configure Cloud]
--------------------------------------------------------------------------------
<!-- Markdown link & img dfn's -->
[Ansible Automation]:/ansible/README.md
[01 Build Host]:/01_Build_Host.md
[02 Build Bastion]:/02_Build_Bastion.md
[03 Build Gateway]:/03_Build_Gateway.md
[04 Setup_Dns]:/04_Setup_DNS.md
[05 Setup HAProxy]:/05_Setup_HAProxy.md
[06 Setup Dhcp]:/06_Setup_DHCP.md
[07 Setup Nginx]:/07_Setup_Nginx.md
[08 Setup Tftpd]:/08_Setup_Tftpd.md
[09 Deploy Cloud]:/09_Deploy_Cloud.md
[10 Configure Cloud]:/10_Configure_Cloud.md
