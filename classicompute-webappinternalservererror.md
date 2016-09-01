<properties 
	pageTitle="My web application shows Internal Server Error or Service Unavailable (50x)"
	description="My web application shows Internal Server Error or Service Unavailable (50x)"
	service="microsoft.classiccompute"
	resource="virtualmachines"
	authors="jluk"
	displayOrder="6"
	selfHelpType="resource"
	supportTopicIds=""
	resourceTags=""	 
	productPesIds=""
	cloudEnvironments="public"
/>

# My web application shows Internal Server Error or Service Unavailable (50x)

## **Recommended steps**
These errors are treated as application errors, so you should troubleshoot them like any on premise hosted application.  

1.	Remote into the instances and check if you can access the web application locally <br> 
This will narrow down know instance encounters the application issue. It could be some instances or all the instances. 
2.	Review the IIS logs for the specific failed request (50x) <br>
The logs are generally located at *“C:\Resources\Directory\guid.role.DiagnosticStore\LogFiles\W3SVC1”*.
3.	Review the Application Logs in the Event Viewer of the same instance with failed request and look for more details about the 50x error
4.	Check with custom logs or use more tools to diagnose the error <br>
If no error/warning event could be found, the exception may be properly handled.
5.  Put a helloworld.html test file into the 'sitesroot' folder <br>
If any startup files like global.asax or web.config have problems, then accessing helloworld.html will have the same issue. 
6.  Enable Failed Request Tracing in IIS to see the detailed error message
7.	Use DebugView to capture exceptions/errors
8.	For further diagnostics, use [DebugDiag] (Add link to https://msdn.microsoft.com/en-us/library/ff420662.aspx), ProcDump or WinDbg to capture memory dumps and review the dumps. It will give pointers where the problem lies in the application.

## **Recommended documents**
