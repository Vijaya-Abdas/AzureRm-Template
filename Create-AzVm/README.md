[Previous page >](../)

# Content
Contain a script sample that demonstrates how to create a VM, with NSG on an existing Vnet/Subnet

# Call Sample
```
#Variable
$AzureRmSubscriptionName="Your Subscription Name"
$DeploymentName="demo"
$RgName="Resource Group Name"


#ARM Deployment
$AzureRmContext = Get-AzSubscription -SubscriptionName $AzureRmSubscriptionName | Set-AzContext -ErrorAction Stop
Select-AzSubscription -Name $AzureRmSubscriptionName -Context $AzureRmContext -Force -ErrorAction Stop

New-AzResourceGroupDeployment -Name $DeploymentName -ResourceGroupName $RgName `
  -TemplateFile .\mainTemplate.json `
  -TemplateParameterFile .\parameters.json

```