# bd_nsx_ansible
A set of playbooks to build a fully functional NSX environment from scratch.
# Dependancies:
- ansible
- nsxansible | Libraries need to be in your working directory. I've included the linrary as of commit 004dc6e
- nsxramlclient - https://github.com/vmware/nsxramlclient
- nsxraml spec - https://github.com/vmware/nsxraml
- ovftool - https://www.vmware.com/support/developer/ovf

## bd_deploy_nsxm
Builds out Management plane. Deploys NSX manager and configures SSO with the vCenter server.

# bd_controller
Deploys 3x NSX controllers to defined cluster.

# bd_nsx_prep
Prepares the defined clusters for NSX, configures VXLAN etc.

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



Playbooks are based off https://github.com/vmware/nsxansible


# Disclaimer
Use at own risk. I've created this to learn python/ansible to be able to build on top of what is available with nsxansible.
