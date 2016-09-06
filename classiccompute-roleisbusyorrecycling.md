<properties
	pageTitle="My Role is Busy or Recycling"
	description="My Role is Busy or Recycling"
	service="microsoft.classiccompute"
	resource="virtualmachines"
	authors="jluk"
	displayOrder=""
	selfHelpType="resource"
	supportTopicIds=""
	resourceTags=""
	productPesIds=""
	cloudEnvironments="public"
/>

# My Role is Busy or Recycling
A role instance may loop between Started, Initializing, Busy, and Stopped. This condition could indicate a problem with your application code, package, or configuration file. <br>
In that case, you should be able to see the status changing every few minutes and the Azure portal may say something like Recycling, Busy, or Initializing. This indicates that there is something wrong with the application that is keeping the role instance from running. <br>

Check the detailed error message [here] (https://manage.windowsazure.com/microsoft.com#Workspaces/CloudServicesExtension/CloudService/ImtiazhWorkerRole/instances) to get details about the error message. <br>

Some common issues that cause roles to be Busy or Recycling include: <br>

* [Role throwing unhandled exceptions while initializing or stopping] (https://blogs.msdn.microsoft.com/kwill/2013/08/20/troubleshooting-scenario-1-role-recycling/) <br>
* [Start-up task causing a Busy state] (https://blogs.msdn.microsoft.com/kwill/2013/09/06/troubleshooting-scenario-3-role-stuck-in-busy/) <br>
* [Start-up task causing a Recycling state](https://blogs.msdn.microsoft.com/kwill/2013/08/26/troubleshooting-scenario-2-role-recycling-after-running-fine-for-2-weeks/) after running fine for some time <br>
* [Missing runtime dependencies] (https://blogs.msdn.microsoft.com/kwill/2013/10/03/troubleshooting-scenario-7-role-recycling/) <br>
* [Failure to cleanup/delete file causing Role Recycle] (https://blogs.msdn.microsoft.com/kwill/2013/09/23/troubleshooting-scenario-6-role-recycling-after-running-for-some-time/) <br>
* [Role returns from Run method when it should block indefinitely] (https://msdn.microsoft.com/library/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) <br>

Refer to documentation below for more information on how to troubleshoot these types of problems. <br>

## **Recommended documents**
[Azure PaaS Compute Diagnostics Data](http://blogs.msdn.com/b/kwill/archive/2013/08/09/windows-azure-paas-compute-diagnostics-data.aspx) <br>
[Common Issues Causing Role Recycles](https://azure.microsoft.com/documentation/articles/cloud-services-troubleshoot-common-issues-which-cause-roles-recycle/) <br>