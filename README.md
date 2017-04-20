# bd_nsx_ansible

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


Playbooks/roles are based off https://github.com/vmware/nsxansible

Dependancies:
- ansible
- nsxansible | Libraries need to be in your working directory. I've included the linrary as of commit 004dc6e 
- nsxramlclient - https://github.com/vmware/nsxramlclient
- nsxraml spec - https://github.com/vmware/nsxraml


# Disclaimer 
Use at own risk. I've created this to learn python/ansible to be able to build on top of what is available with nsxansible.

