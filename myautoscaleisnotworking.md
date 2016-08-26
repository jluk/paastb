
# My autoscale is not working

## **Recommended steps**
Instances not scaling based on CPU or other default metrics <br>
Example: CPU>80% and have the TimeWindow set as 45 minutes. <br> 
Scaling will happen only when the average CPU value for all role instances is more than 80% for at least 45 minutes.

1. Reduce the TimeWindow property <br>
This will cause scaling to happen more frequently. The default TimeWindow/Duration property is 30 minutes (New portal) or 45 minutes(Classic Portal). <br>

[About autoscale best practices] (https://azure.microsoft.com/en-us/documentation/articles/insights-autoscale-best-practices/) <br>
[About scaling Cloud Services in Portal] (https://azure.microsoft.com/en-us/documentation/articles/cloud-services-how-to-scale-portal/)

Autoscale seems to be successful but scaling is not happening <br>

1. Ensure that all roles instances are in "Ready" state <br>
2. Try to scale manually <br>
3. Check the number of available cores <br>
If it has reached the maximum compute quota limit for the subscription, you can increase the subscription compute quota limit by calling Microsoft.
4. This may happen when the cluster you are deployed to has reached capacity limits or does not have the type of compute cores that you are requesting <br>
    a. Try to scale in smaller increments
    b. Create a new host service and redeploy to it with the maximum instances needed. Scale down after the initial deployment if needed. Deploying with maximum instances ensures that the cluster has the capacity you may need.

[About Cloud Services allocation failures] (https://azure.microsoft.com/en-us/documentation/articles/cloud-services-allocation-failures/) <br>

When using Autoscale, I get error message 'Metrics data not available' <br>
Autoscale requires monitoring data from the Role Instances in order to scale. At times there may be a delay in data collection. When autoscale cannot get the metrics data, it will scale to the 'Default Value' if it is higher than the current instance count. This issue will correct itself when autoscale starts receiving the Metrics data.

1. If this is causing production issues, turn off autoscale and manually scale to the number of instances needed <br>
2. Set your scaling TimeWindow (duration) to 30 minutes or higher <br>

## **Recommended documents**
https://social.msdn.microsoft.com/Forums/azure/en-US/bc2048c4-8d49-4c54-b150-f263808c4b7a/notification-could-not-automatically-scale-xxx-because-monitoring-data-was-not-found?forum=windowsazuremanagement http://rickrainey.com/2013/12/15/auto-scaling-cloud-services-on-cpu-percentage-with-the-windows-azure-monitoring-services-management-library/