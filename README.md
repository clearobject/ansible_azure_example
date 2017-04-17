Introduction
===

This demo walks through creating two new instances in Azure and installing apache
on each of them. This demo covers all Azure modules currently avaiable in Ansible 2.3

Inventory
===

In order to authenticate to Azure, you will either need an AD setup that you can authenticate to, or we can create an identity in Azure. Microsoft provides a detailed guide on how to create an identity. Once you can successfully authenticate to Azure cloud, you can move on to the next steps.
The four values you will need to authenticate are:

AZURE_CLIENT_ID (user id)
AZURE_SECRET (user pass)
AZURE_SUBSCRIPTION_ID (account id)
AZURE_TENANT (AD id)

We will be setting these as environment variables, since this is how we work in production. You can also set these values in an INI style file in ~/.azure/credentials

Modules Used (Azure)
===
azure - create or terminate a virtual machine in azure
azure_rm_networkinterface - Manage Azure network interfaces.
azure_rm_publicipaddress - Manage Azure Public IP Addresses.
azure_rm_resourcegroup - Manage Azure resource groups.
azure_rm_securitygroup - Manage Azure network security groups.
azure_rm_storageaccount - Manage Azure storage accounts.
azure_rm_storageblob - Manage blob containers and blob objects.
azure_rm_subnet - Manage Azure subnets.
azure_rm_virtualmachine - Manage Azure virtual machines.
azure_rm_virtualnetwork - Manage Azure virtual networks.

Executing a Playbook
===

```
ansible-playbook -i inventory/azure.py playbooks/<playbook_name>
```

Available Playbooks
===
name | description
--- | ---
setup | Creates a set of 2 demo instances
teardown | Cleans everything from the demo up
file_upload | Uploads an index page into azure storage
apache | Configures apache on the instances
