<properties 
	pageTitle="My application is slow"
	description="My application is slow"
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

# My application is slow

## **Recommended steps**
1.	Keep the external dependencies (SQL Azure, Azure Redis Cache, etc.) that the application accesses in the same region <br>
If the application has a lot of external resources, network delays may cause slowness.
2.	Review operating system level metrics such as CPU, memory usage, IO, and network <br>
If any resource has consistently high utilization, your application may be needing more resources than the current hardware provides. Scale out or scale up if you see resource constraints. 
3.	Review your application error logs, traces, and metrics <br>
This can determine if there are any application bottlenecks causing performance issues. A quick way to recover from one-time issues is to restart your application and machine.
4.	For further diagnostics, use [DebugDiag] (https://msdn.microsoft.com/en-us/library/ff420662.aspx), ProcDump or WinDbg <br> 
These programs capture memory dumps and give pointers to where the problem lies in the application.

## **Recommended documents**
[Troubleshoot using performance-analysis tool to isolate CPU- and memory-related performance issues](https://channel9.msdn.com/Series/PerfView-Tutorial)<br>
[Use Perfview to collect and analyze data for performance bottlenecks](http://www.microsoft.com/download/details.aspx?id=28567)<br>
[Use the Debug Diagnostics tool to troubleshoot a process that has stopped responding](https://support.microsoft.com/kb/919792)