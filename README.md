Step 1 : Open the AWS System Manager Parameter Store from the AWS Console, and create the following parameter using Standard Tier of type String:
Name: UserName
Value: JohnDoe
 
Step 2 : From the AWS Console, create an S3 bucket to be used in the next step.
 
Step 3 : Using a single AWS CloudFormation template (YAML or JSON), write a custom Lambda function in Python or Java called “exercise-lambda” that will:
    Retrieve SSM Parameter Store the key/value pair created above in step 1
    Store this retrieved key/value pair into a file in the S3 bucket created in Step 2.

Hints:
-       don’t forget to send a response back from the custom Lambda function to CloudFormation.
-       Be sure to handle Delete events in order to prevent hangs during stack deletion
-       Be sure to grant appropriate permissions (not excessive permissions) to the lambda function so that CloudWatch logs will be created during stack creation.  These logs can be used for troubleshooting the lambda function. 
-       Do not choose an IAM role in CloudFormation – Configure stack options when creating the stack.  The CloudFormation template should define any necessary permissions.
