Cloudformation Drift detection Tool
====================================

Step 0)
Use the [Lamda Layer magic](https://github.com/kisst/CFN-CR-PythonLambdaLayer)  to create a Lambda Layer with the latest boto3

Step 1)
Scan all region for CFN Stacks, and trigger 'detect drift'

Step 2)
Run trough all CFN stacks and check drift status

Step 3)
If any stack is drifted, the publish a message to SNS about it

###Deployment

Deploy the CFN template `CFN-Drift-Reports.yaml` where:

 - **CronLine1** is the times when the detect is kicked off
 - **CronLine2** is the times when the statuc check is kicked off ( e-mail's are sent this time ) 
 - **EmailAddress** is the address where notifications should be sent about drifted stacks