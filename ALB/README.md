## Naming conventions

1. Stack name
   -max character length of the stack name should less than or equal to 52
   -should contain only simple letters
   -words separated by hyphens
   -prefix: peace-
   -suffix: -pipeline
   peace-${project-name}-${env1-env2}-pipeline
   ex: peace-ws-dev-pipeline


stack name is equal to the parameter json file name
for the parameter file give the specific path (dev/dev-qa/st/stg-prod) and give the pipeline name

## Steps to run create/update stack

install AWS cli v2
open the project folder FargatePipeline
open terminal
add aws security keys
run below commands
to create a stack: create-stack
to update a stack: update-stack


## thc-nota-ws

# dev
aws cloudformation create-stack    --stack-name thc-nota-dev-alb    --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml     --parameters file://ALBParameters/dev/thc-nota-dev-alb.json --capabilities CAPABILITY_NAMED_IAM
aws cloudformation update-stack    --stack-name thc-nota-dev-alb    --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml     --parameters file://ALBParameters/dev/thc-nota-dev-alb.json --capabilities CAPABILITY_NAMED_IAM


# qa
aws cloudformation create-stack    --stack-name thc-nota-qa-alb  --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml     --parameters file://ALBParameters/qa/thc-nota-qa-alb.json --capabilities CAPABILITY_NAMED_IAM
aws cloudformation update-stack    --stack-name thc-nota-qa-alb  --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml     --parameters file://ALBParameters/qa/thc-nota-qa-alb.json --capabilities CAPABILITY_NAMED_IAM



# stg
aws cloudformation create-stack    --stack-name thc-nota-stg-alb  --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml      --parameters file://ALBParameters/stg/thc-nota-stg-alb.json --capabilities CAPABILITY_NAMED_IAM
aws cloudformation update-stack    --stack-name thc-nota-stg-alb  --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml     --parameters file://ALBParameters/stg/thc-nota-stg-alb.json --capabilities CAPABILITY_NAMED_IAM


# prod
aws cloudformation create-stack    --stack-name thc-nota-prod-alb  --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml     --parameters file://ALBParameters/prod/thc-nota-prod-alb.json --capabilities CAPABILITY_NAMED_IAM
aws cloudformation update-stack    --stack-name thc-nota-prod-alb  --template-body file://THC-NOTA-WEB-SERVICE-ALB.yml     --parameters file://ALBParameters/prod/thc-nota-prod-alb.json --capabilities CAPABILITY_NAMED_IAM

