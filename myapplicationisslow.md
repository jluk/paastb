# My application is slow

## **Recommended steps**
1.	Keep the external dependencies (SQL Azure, Azure Redis Cache, etc.) that the application accesses in the same region. <br>
If the application has a lot of external resources, network delays may cause slowness.
2.	Review operating system level metrics such as CPU, memory usage, IO, and network <br>
If any resource has consistently high utilization, your application may be needing more resources than the current hardware provides. Scale out or scale up if you see resource constraints. 
3.	Review your application error logs, traces, and metrics <br>
This can determine if there are any application bottlenecks causing performance issues. A quick way to recover from one-time issues is to restart your application and machine.
4.	For further diagnostics, use [DebugDiag] (https://msdn.microsoft.com/en-us/library/ff420662.aspx), ProcDump or WinDbg <br> 
These programs capture memory dumps and give pointers to where the problem lies in the application.

## **Recommended documents**