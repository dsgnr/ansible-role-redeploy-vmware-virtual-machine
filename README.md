# Ansible Role: Redeploy VMware Virtual Machine with Netbox IPAM

[![Build Status](https://travis-ci.org/dsgnr/ansible-role-redeploy-vmware-virtual-machine-with-netbox.svg?branch=master)](https://travis-ci.org/dsgnr/ansible-role-redeploy-vmware-virtual-machine-with-netbox)

This role allows the removal of a virtual machine and redeployment of a virtul machine template within vCenter. Information about the guest is gathered from IPAM, like the OS, memory and vcpu information. To change the operating system, simply update the virtual machine inside Netbox and run the playbook.

This playbook is used in my homelab. It's not perfect and can definitely be improved. Don't expect this playbook to work for you out the box as our environments will differ.

## Requirements

- vCenter appliance
- vCenter templates
- Netbox IPAM

## Role Variables

- vault_ipam_url: The URL of your IPAM
- vcenter_hostname: The hostname of your venter appliance
- vcenter_user: Your vCenter username
- vcenter_pass: Your vCenter password
- vmnetwork: The VM network within venter
- vmtemplate: The template you'd like to deploy
- vmnetmask: The VMs netmask
- vmgateway: The VMs gateway

## Dependencies

None.

## Example Playbook

    - hosts: all
      become: true
      
      roles:
        - redeploy-vm

## License

GNUv3

## Author Information

This role was created by [Dan Hand](https://danielhand.io).

