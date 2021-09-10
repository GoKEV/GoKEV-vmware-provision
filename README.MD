[![GoKEV](http://GoKEV.com/GoKEV200.png)](http://GoKEV.com/)

<div style="position: absolute; top: 40px; left: 200px;">

# motd-splash

This set of roles and playbooks is a relatively simple self-service provisioning example.  Use the `vmware-provision.yml`, which will include necessary playbooks and roles below it.

## Your job template should include these extra vars.  Customize these extra vars to what your VMware environment uses:
<pre>
vm_network: MyNICName
os_type: linux
vc_datacenter: GoKEV
vc_datastore: GoKEVLUN
</pre>

## Your job template survey should query for these vars:
<pre>
vm_cpu_count: '1'
vm_disk_size: '50'
vm_name: |-
  gokev-win10-01
  gokev-win10-02
vm_network: GoKEV-NET
vm_ram_mb: '4096'
vm_template: TEMPLATE-GoKEV-RHEL8
</pre>


## Notes on extra vars passed:
The OS type "linux" or "windows" -- after provisioning the new VM, it will include subsequent roles `prep-new-windows` or `prep-new-linux`
The value for `vm_name` can be whitespace-separated system names or a dict list.  If you enter `server01 server02 server03`, this playbook will parse that into three individual servers


Author Information
------------------

Kevin Holmes :: kev@GoKEV.com

This project was created in 2018 by [Kevin Holmes](http://GoKEV.com/).

- Update 2019-05-10 :: After the new Red Hat logo was released at Red Hat Summit 2019, the shadowman style logo was replaced by the new RHT logo

