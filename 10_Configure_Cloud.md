--------------------------------------------------------------------------------
  + [00 Introduction]
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
```sh
 oc get csr -ojson | jq -r '.items[] | select(.status == {} ) | .metadata.name' | xargs oc adm certificate approve
 oc patch configs.imageregistry.operator.openshift.io cluster --type merge --patch '{"spec":{"storage":{"emptyDir":{}}}}'
 oc get -n openshift-ingress-operator ingresscontrollers/default -o jsonpath='{$.spec.replicas}'
 oc patch -n openshift-ingress-operator ingresscontroller/default --patch '{"spec":{"replicas": 1}}' --type=merge ingresscontroller.operator.openshift.io/default patched
```

```sh
 htpasswd -c -B -b users.htpasswd ocadmin admin
 oc create secret generic htpass-secret --from-file=htpasswd=./users.htpasswd -n openshift-config
 oc apply -f ~/.ccio/ocp-mini-stack/module/cloudctl/aux/config/htpasswd.yaml
 oc adm policy add-cluster-role-to-user cluster-admin ocadmin
 oc delete secrets kubeadmin -n kube-system
```
--------------------------------------------------------------------------------
#### Install Palemoon on CloudCtl
  - Workaround for self signed certificate complaints
```sh
dnf install -y https://download.copr.fedorainfracloud.org/results/bgstack15/palemoon/fedora-30-x86_64/00979202-palemoon/palemoon-28.6.1-1.src.rpm
```
#### Open OCP Console with Palemoon
  - USER:PASSWD: ocpadmin:admin
```sh
palemoon https://console-openshift-console.apps.ocp.ministack.dev &
```
--------------------------------------------------------------------------------
## Testing
#### Istio
```sh
https://github.com/raffaelespazzoli/openshift-enablement-exam/tree/master/misc4.0/ServiceMesh
oc get pods -n istio-system 
```
```
https://docs.openshift.com/container-platform/4.3/service_mesh/service_mesh_install/customizing-installation-ossm.html#customize-installation-ossm
https://docs.openshift.com/container-platform/4.3/service_mesh/service_mesh_day_two/prepare-to-deploy-applications-ossm.html#deploying-applications-ossm
```
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
