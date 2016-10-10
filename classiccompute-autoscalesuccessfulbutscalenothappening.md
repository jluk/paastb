<properties 
	pageTitle="Autoscale seems to be successful but scaling is not happening"
	description="Autoscale seems to be successful but scaling is not happening"
	service="microsoft.classiccompute"
	resource="domainnames"
	authors="jluk"
	displayOrder="5"
	selfHelpType="resource"
	supportTopicIds=""
	resourceTags=""	 
	productPesIds=""
	cloudEnvironments="public"
/>

# Autoscale seems to be successful but scaling is not happening
Below is a collection of solutions and explanations for why scaling may not occur. <br>

## **Recommended steps**
* Ensure that all roles instances are in **Ready** state. <br>
Autoscale will only occur if all roles are in Ready state. <br>
* Try to scale manually and if it succeeds, the autoscale profile may be configured incorrectly. <br>
Multiple autoscale profiles can affect the behavior of autoscale. [Creating and managing autoscale profiles] (https://azure.microsoft.com/documentation/articles/insights-autoscale-best-practices/#autoscale-best-practices) should be done from the same portal as each portal has unique default autoscale profiles. <br>
* Try to scale in smaller increments as the cluster where your application is deployed may not have enough free cores. <br>
* Increase the subscription quota limit by [contacting Microsoft] (data-blade:Microsoft_Azure_Support.NewSupportRequestBlade) as autosacle cannot succeed without sufficient compute quota. <br>
* Create a new host service and redeploy to it with the maximum instances needed. Scale down afterwards if needed. <br>
Deploying with maximum instances ensures the cluster has the capacity you may require. <br>

## **Recommended documents**
[About autoscale best practices] (https://azure.microsoft.com/documentation/articles/insights-autoscale-best-practices/#autoscale-best-practices)
[About Cloud Services allocation failures] (https://azure.microsoft.com/documentation/articles/cloud-services-allocation-failures/) <br>