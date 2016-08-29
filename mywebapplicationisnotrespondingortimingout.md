# My web application is not responding or timing out  

## **Recommended steps**
1.	Check the Cloud Service availability on Azure Portal <br>
Check all role instances are in “Ready” state. If not in ready state, refer back to the troubleshooting blade.
2.	RDP into the role instance and make sure that the application process (w3wp) in Task Manager is running <br>
If the w3wp process does not show in Task Manager, then go to [IIS Manager] (https://technet.microsoft.com/en-us/library/jj635847(v=ws.11).aspx) and restart the application. 
3.	Check the http response code you get in the browser <br>
50x errors are application related issues, refer back to the troubleshooting blade.
4.	Check the default ports 80 (for http) and 443 (for https) are accessible. Use TELNET or TCPING to ensure that the w3wp process is listening on it. <br>
If your web application is accessible locally but not externally, it could be a network related issue. 
