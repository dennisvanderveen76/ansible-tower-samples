Manage Cisco devices with Ansible
=================================

Demo of using Ansible to manage the configuration of Cisco devices using Ansible CLI config and feature modules.


## Description

The playbooks are designed to dynamically _create_ and _assign_ VLANs in the network:
- Switches
    - create VLANs
    - assign VLANs to access ports and trunks
- Routers:
    - create VLANs as subinterfaces on the uplinks to the switches
    - configure a virtual high available IP addresses (VRRP) for each VLAN
    - configure DHCP in the routers for each VLAN

Important Ansible files:
- VLAN definitions: 
    - `inventory/group_vars/cisco_ios/vlan_definitions.yml`
- Switch port definitions: 
    - `inventory/host_vars/S1.yml`
    - `inventory/host_vars/S2.yml`
- Main playbook:
    - `playbooks/run_all.yml`


## Install
To install Ansible and Python:
- install the [UV](https://docs.astral.sh/uv/getting-started/installation/) Python package manager
- run `uv sync` to install Python and all dependencies including Ansible
- activate the virtual environment: `source .venv/bin/activate`

`CML_LAB_Ansible_Demo_IOL.yaml` can be imported as lab into Cisco Modelling Labs (CML). It uses a bridge to your network. Replace all IP addresses in the YAML and Ansible inventory to accommodate your own lab.
