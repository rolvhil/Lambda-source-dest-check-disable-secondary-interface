# Lambda-source-dest-check-disable-secondary-interface
lambda to disable secondary interfaces created by vpc cni

Cfn Template does

1. Creates Cloudwatch event rule that watches for CreateNetworkInterface and subnetid on CloudTrail.
2. Creates Lambda function that modifies the source/destination check to false based on the ENI ID of the created interface.
3. Cloudwatch event as trigger to lambda

Note: The LambdaBasicExecutionRole must have the ec2:ModifyNetworkInterfaceAttribute and ec2:DescribeNetworkInterfaces permission
