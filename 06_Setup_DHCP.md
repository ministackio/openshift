[![Alpine Build](https://img.shields.io/github/workflow/status/containercraft/ccio-dnsmasq/DockerHubBuild/alpine?label=Alpine%20Build)](https://github.com/containercraft/ccio-dnsmasq/actions) [![Docker Pulls](https://img.shields.io/docker/pulls/containercraft/ccio-dnsmasq?label=DockerHub%20Pulls)](https://hub.docker.com/r/containercraft/ccio-dnsmasq)<br>
[Find on DockerHub](https://hub.docker.com/r/containercraft/ccio-dnsmasq) || [Find on Github](https://github.com/containercraft/ccio-dnsmasq)

### Prerequisites:
  + [00 Introduction]
  + [01 Build Host]
  + [02 Build Bastion]
  + [03 Build Gateway]
  + [04 Setup_Dns]
  + [05 Setup HAProxy]
--------------------------------------------------------------------------------
    
# Part 06 -- [Dnsmasq]: DHCP & DNS Service
####    Step.01 Launch [Dnsmasq] on [Alpine Linux] Container with [Podman]
```sh
sudo podman run \
    --rm                                                                                                      \
    --detach                                                                                                  \
    --cap-add=NET_ADMIN                                                                                       \
    --name    ocp-dnsmasq                                                                                     \
    --publish ${ocp_ministack_SUBNET}.3:53:53/udp                                                             \
    --volume  ~/.ccio/ocp-mini-stack/module/dnsmasq/aux/config/dnsmasq.hosts:/etc/hosts                       \
    --volume  ~/.ccio/ocp-mini-stack/module/dnsmasq/aux/config/dnsmasq.conf:/etc/dnsmasq.conf                 \
    --volume  ~/.ccio/ocp-mini-stack/module/dnsmasq/aux/config/dnsmasq.resolv:/etc/resolv.conf                \
  docker.io/containercraft/ccio-dnsmasq:latest
```
    
    
---------------------------------------------------------------------------------
    
### Next Steps:
  + [07 Setup Nginx]
  + [08 Setup Tftpd]
  + [09 Deploy Cloud]
  + [10 Configure Cloud]
    
---------------------------------------------------------------------------------
    
######  + [Repo Module] Index
```sh
.
├── aux
│   └── config
│       ├── dnsmasq.conf
│       ├── dnsmasq.ethers
│       ├── dnsmasq.hosts
│       ├── dnsmasq.leases
│       └── dnsmasq.resolv.conf
└── README.md
```

<!-- Markdown link & img dfn's -->
[Repo Module]:/module/dnsmasq
[alpine linux]: https://alpinelinux.org/
[dnsmasq]: http://www.thekelleys.org.uk/dnsmasq/doc.html
[podman]: https://podman.io
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
[00 Introduction]:/00_Introduction.md
<!-- Markdown link & img dfn's -->
[00 Introduction]:/00_Introduction.md
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