# infrastructure

First copy the template from piazza and set the attribute value.

## CREATE CLOUDFORMATION STACK¶

aws cloudformation create-stack \

  --stack-name csye6225demo \

  --parameters ParameterKey=InstanceTypeParameter,ParameterValue=t2.micro \

  --template-body file://cf.json

## DELETE CLOUDFORMATION STACK¶

aws cloudformation delete-stack --stack-name csye6225demo

## WAIT FOR CLOUDFORMATION STACK DELETION¶

aws cloudformation wait stack-delete-complete --stack-name csye6225demo

## CREATE IAM STACK

aws cloudformation create-stack --stack-name iam-stack --template-body file://iam.json --capabilities CAPABILITY_NAMED_IAM
