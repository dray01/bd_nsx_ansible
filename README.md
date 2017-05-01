# bd_nsx_ansible
A set of playbooks to build a fully functional NSX environment from scratch.
# Dependancies:
- ansible
- nsxansible | Libraries need to be in your working directory. I've included the library as of commit 004dc6e https://github.com/vmware/nsxansible
- nsxramlclient - https://github.com/vmware/nsxramlclient
- nsxraml spec - https://github.com/vmware/nsxraml
- ovftool - https://www.vmware.com/support/developer/ovf

# Playbooks

## bd_deploy_nsxm
Builds out Management plane. Deploys NSX manager and configures SSO with the vCenter server.

## bd_controller
Builds control plane. Deploys 3x NSX controllers to defined cluster.

## bd_cluster_prep
Builds control plane to clusters. Prepares the defined clusters for NSX, configures VXLAN etc.

## bd_full_top
Build out NSX data plane environment. ESG, DLR and logical networks. Configuring OSPF from DLR <-> ESG and ESG <-> physical.

		------------
		|   PHYS   |
		------------
		     | (area 0)
		     |
		------------
		|   ESG    |
		------------
		     |
		     | (area 10)
		------------
		|   DLR    |
		------------
             | | | | | | (Logical switches defined by dlr_networks)

## bd_allinone
Playbook to based on all of the above playbooks to build an NSX instance from scratch.

Playbooks are based off https://github.com/vmware/nsxansible

##bd_build_from_scratch
Playbook to call 3 roles inside the role folder. Currently not working in my lab due to python/ramlclient error.

# Disclaimer
Use at own risk. I've created this to learn python/ansible to be able to build on top of what is available with nsxansible.
