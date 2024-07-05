## Naming conventions

1. Stack name
   -max character length of the stack name should less than or equal to 52
   -should contain only simple letters
   -words separated by hyphens
   -prefix: peace-
   -suffix: -pipeline
   peace-${project-name}-${env1-env2}-pipeline


2. IsApprovalNeeded : true
   will add manual approval, only if the pipeline has two envs to be deployed
   ex: dev-qa, stg-prod

3. IsCloudWatchEnabledToDevQa: true
   will add cloud watch trigger only if the pipeline type is dev-qa

4. IsDeployBuildSpecFromRoot: true
   will get build spec from the root of the project


stack name is equal to the parameter json file name
for the parameter file give the specific path (dev/dev-qa/qa-prod) and give the pipeline name

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
aws cloudformation create-stack    --stack-name thc-nota-ws-dev-fargate    --template-body file://PEACE-WEB-SERVICE-FARGATE-TASK.yml     --parameters file://ECSParameters/dev/thc-nota-ws-dev-fargate.json --capabilities CAPABILITY_NAMED_IAM
aws cloudformation update-stack    --stack-name thc-nota-ws-dev-fargate    --template-body file://PEACE-WEB-SERVICE-FARGATE-TASK.yml     --parameters file://ECSParameters/dev/thc-nota-ws-dev-fargate.json --capabilities CAPABILITY_NAMED_IAM
# qa
aws cloudformation create-stack    --stack-name thc-nota-ws-qa-fargate     --template-body file://PEACE-WEB-SERVICE-FARGATE-TASK.yml     --parameters file://ECSParameters/qa/thc-nota-ws-qa-fargate.json --capabilities CAPABILITY_NAMED_IAM
aws cloudformation update-stack    --stack-name thc-nota-ws-qa-fargate     --template-body file://PEACE-WEB-SERVICE-FARGATE-TASK.yml     --parameters file://ECSParameters/qa/thc-nota-ws-qa-fargate.json --capabilities CAPABILITY_NAMED_IAM

# stg
aws cloudformation create-stack    --stack-name thc-nota-ws-stg-fargate     --template-body file://PEACE-WEB-SERVICE-FARGATE-TASK.yml     --parameters file://ECSParameters/stg/thc-nota-ws-stg-fargate.json --capabilities CAPABILITY_NAMED_IAM
aws cloudformation update-stack    --stack-name thc-nota-ws-stg-fargate     --template-body file://PEACE-WEB-SERVICE-FARGATE-TASK.yml     --parameters file://ECSParameters/stg/thc-nota-ws-stg-fargate.json --capabilities CAPABILITY_NAMED_IAM

# prod
aws cloudformation update-stack    --stack-name thc-nota-ws-prod-fargate     --template-body file://PEACE-WEB-SERVICE-FARGATE-TASK.yml     --parameters file://ECSParameters/prod/thc-nota-ws-prod-fargate.json --capabilities CAPABILITY_NAMED_IAM
