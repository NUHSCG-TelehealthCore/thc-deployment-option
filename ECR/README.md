## Naming conventions

1. Stack name
   -max character length of the stack name should less than or equal to 52
   -should contain only simple letters
   -words separated by hyphens
   -prefix: peace-
   -suffix: -pipeline
   pcar-${project-name}-${env1-env2}-pipeline
   ex: peace-web-app-dev-pipeline

   

stack name is equal to the parameter json file name

## Steps to run create/update stack

install AWS cli v2
open the project folder WebAppPipeline
open terminal
add aws security keys
run below commands
to create a stack: create-stack
to update a stack: update-stack

## dev stack
aws cloudformation create-stack --stack-name peace-ws-dev-ecr  --template-body file://PEACE-WEB-SERVICE-ECR.yml  --parameters file://ECRParameters/dev/peace-ws-dev-ecr.json --capabilities CAPABILITY_NAMED_IAM

aws cloudformation update-stack --stack-name peace-ws-dev-ecr   --template-body file://PEACE-WEB-SERVICE-ECR.yml  --parameters file://ECRParameters/dev/peace-ws-dev-ecr.json --capabilities CAPABILITY_NAMED_IAM

## qa stack

aws cloudformation create-stack --stack-name peace-ws-qa-ecr --template-body file://PEACE-WEB-SERVICE-ECR.yml  --parameters file://ECRParameters/qa/peace-ws-qa-ecr.json --capabilities CAPABILITY_NAMED_IAM

## stg stack

aws cloudformation create-stack --stack-name peace-ws-stg-ecr --template-body file://PEACE-WEB-SERVICE-ECR.yml  --parameters file://ECRParameters/stg/peace-ws-stg-ecr.json --capabilities CAPABILITY_NAMED_IAM

## prod stack

aws cloudformation create-stack --stack-name thc-nota-ws-prod-ecr --template-body file://THC-NOTA-WEB-SERVICE-ECR.yml  --parameters file://ECRParameters/prod/thc-nota-ws-prod-ecr.json --capabilities CAPABILITY_NAMED_IAM


