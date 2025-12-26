# Terraform-deploying-AZ-resources
Using this repo to deploy resources to Azure sub via Terraform IaC


basically what I did here was deploy a resource group named "myTFResourceGroup" via the terraform. using terraform init (initialize), terraform plan (plan out what will be done), & terraform apply (this will confirm the changes that I wish to commit)

I then made a change manually on the portal (added a tag to the RG) to see that change reflect on my terraform state file as that is the original file in which I deployed the rg with and should technically be the standard held across this project. 

When trying to run terraform plan after making the manual change, it informed me that a tag as was added and that it wants to convert it back as the original state file should be the standard and the template used to move forward.

## azurerm_resource_group.rg will be updated in-place
  ~ resource "azurerm_resource_group" "rg" {
        name     = "myTFResourceGroup"
      ~ tags     = {
          - "dummytest" = "dumb" -> null
        }
        # (1 unchanged attribute hidden)
##  }"
