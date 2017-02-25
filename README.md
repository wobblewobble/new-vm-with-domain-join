# Create a new VM and join it to an existing domain.

This template creates a new VM and joins it to an existing AD domain, using an existing VNET and existing storage account. The AD domain must have
connectivity to the VNET. The DNS definitions on the VNET must enable
the new VM to resolve the AD domain. 

One-click deployment to Azure:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fwkasdorp%2Fnew-vm-with-domain-join%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

Warning: this template **creates one running VM**. 
Make sure to deallocate it when you are done to avoid incurring costs. 

The existing VNET and Storage Groups can be in different Resource Groups. 
This enables a neat trick: after you are done with the VMs you can remove
 the entire RG and its contents in one shot, 
instead of having to pick the resources from the existing RG one by one. 

The template, unusually, does not ask for the administrator name 
and password for the new VM. This is because the VM will 
be joined to a domain and the local Admin account is not needed.
