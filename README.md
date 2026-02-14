SL VM Hardcoded 

az deployment group create -g ODL-az-400-2071575 -f slvmhardcoded.json 

az vm list --output table

az vm delete -g ODL-az-400-2071575 -n Bipeen-vm --yes --force-deletion yes



<img width="506" height="182" alt="image" src="https://github.com/user-attachments/assets/6e158e8f-5a1b-4ded-a172-0a742a6c6d16" />


Storage Account
========================
az deployment group create --name noparameter --resource-group ODL-az-400-2071575 --template-file storagedemo.json

<img width="943" height="95" alt="image" src="https://github.com/user-attachments/assets/931075df-8f93-4ebd-a689-822353e07724" />

az deployment group create --name noparameter --resource-group ODL-az-400-2071575 --template-file storagedemoreusable.json --parameters storageName=crtrlstr43sewdr

<img width="942" height="383" alt="image" src="https://github.com/user-attachments/assets/fed41163-8301-486d-b758-3b15d9d0208d" />

Export entire Resource Group
===================================
az group export --name ODL-az-400-2071575 > exported-template.json
<img width="716" height="424" alt="image" src="https://github.com/user-attachments/assets/7fa9f741-9b9e-4baf-8188-2881d0393c86" />

# Delete the Storage Account manually  and redeploy with the following command ( When prompted give new Name )

az deployment group create -g ODL-az-400-2071575 -f exported-template.json

<img width="782" height="458" alt="image" src="https://github.com/user-attachments/assets/83e95ad6-186f-4ef4-951f-0f630f87c66d" />


