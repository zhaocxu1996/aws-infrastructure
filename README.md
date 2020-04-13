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

## CREATE NETWORK STACK

aws cloudformation create-stack --stack-name network-stack --template-body file://networking.json

## CREATE IAM STACK

aws cloudformation create-stack --stack-name policy-stack --template-body file://iam.json --capabilities CAPABILITY_NAMED_IAM

## BUILD AUTO SCALING STACK

aws cloudformation create-stack --stack-name test --template-body file://auto-scaling.json --capabilities CAPABILITY_NAMED_IAM --parameters ParameterKey=keyname,ParameterValue=awsdemo

## Importing Certificates into AWS Certificate Manager

aws iam upload-server-certificate --server-certificate-name certificate_prod --certificate-body file://prod_zhaocxu_me.crt --private-key file://private-key.pem --certificate-chain file://prod_zhaocxu_me.ca-bundle --profile prod
