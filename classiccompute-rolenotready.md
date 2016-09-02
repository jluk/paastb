<properties
	pageTitle="worker role (paas)/application and service availability/role startup and recycling"
	description="worker role (paas)/application and service availability/role startup and recycling"
	service="microsoft.classiccompute"
	resource="domainnames"
	authors="aashu"
	displayOrder=""
	selfHelpType="generic"
	supportTopicIds="32422590"
	resourceTags=""
	productPesIds="13185"
	cloudEnvironments="public"
/>

# Role State Busy or Restarting
A role instance may loop between Started, Initializing, Busy, and Stopped. This condition could indicate a problem with your application code, package, or configuration file. <br>
In that case, you should be able to see the status changing every few minutes and the Azure portal may say something like Recycling, Busy, or Initializing. This indicates that there is something wrong with the application that is keeping the role instance from running. <br>
 
Check the detailed error message here (deep link to the cloud service instances extension the AUX portal: e.g. https://manage.windowsazure.com/microsoft.com#Workspaces/CloudServicesExtension/CloudService/ImtiazhWorkerRole/instances) to get details about the error message.

Some common issues that cause roles to not be Ready include: <br>

1. A role throwing unhandled exceptions while initializing or stopping <br>
2. A start-up task causing a Busy state <br>
3. A start-up task causing a Recycling state after running fine for some time <br>
4. Missing runtime dependencies <br>
5. Failure to cleanup/delete file causing Role Recycle <br>
6. Role returns from Run method <br>

For more information on how to troubleshoot for this problem, refer to the documentation below. <br>

## **Recommended documents**
[Common issues that cause roles to recycle](https://azure.microsoft.com/documentation/articles/cloud-services-troubleshoot-common-issues-which-cause-roles-recycle/)<br>
[Common steps to troubleshoot & address Cloud Service roles that fail to start](https://azure.microsoft.com/documentation/articles/cloud-services-troubleshoot-roles-that-fail-start/)<br>
[Troubleshoot Cloud Service deployment problems](https://azure.microsoft.com/documentation/articles/cloud-services-troubleshoot-deployment-problems/)<br>
[Troubleshoot Cloud Services common issues - role recycling & startup](http://blogs.msdn.com/b/kwill/archive/2013/08/09/windows-azure-paas-compute-diagnostics-data.aspx)