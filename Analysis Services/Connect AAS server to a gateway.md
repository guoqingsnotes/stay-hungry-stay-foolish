// Connect AAS server to a gateway

1.	To execute PowerShell script, we need to install AZ module using below command.
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
 
2.	Get the gateway resource ID.
Connect-AzAccount -Tenant $TenantId -Subscription $subscriptionIdforGateway -Environment "AzureCloud"
$GatewayResourceId = $(Get-AzResource -ResourceType "Microsoft.Web/connectionGateways" -Name $gatewayName).ResourceId
 
    $TenantId: Tenant ID found in AAD
    $subscriptionIdforGateway: Subscription ID of ‘CLP Workload Prod’
    $gatewayName: gateway name VPBIG-EASP01PD
 
3.	Configure AAS server to connect to gateway.
Connect-AzAccount -Tenant $TenantId -Subscription $subscriptionIdforAzureAS -Environment "AzureCloud"
Set-AzAnalysisServicesServer -ResourceGroupName $RGName -Name $servername -GatewayResourceId $GatewayResourceId
 
    $TenantId: Tenant ID found in AAD
    $subscriptionIdforAzureAS: Subscription ID of AAS’s subscription
    $RGName: Resource Group name of AAS
    $servername: AAS server name
