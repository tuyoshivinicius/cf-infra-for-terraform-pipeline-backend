# infraestrutura para o backend de pipeline terraform

## passo a passo
1. criar uma nova stack cloudformation importando infrastructure.yml (console ou cli)
2. definir parameter "Env" com o ambiente respectivo.

No exemplo abaixo iremos criar um backend pra cada ambiente e em regiões distintas

## criar stack dev
aws cloudformation create-stack --stack-name terraform-infrastructure --template-body file://infrastructure.yaml --parameters ParameterKey=Env,ParameterValue=dev --region us-west-1

## criar stack prod
aws cloudformation create-stack --stack-name terraform-infrastructure --template-body file://infrastructure.yaml --parameters ParameterKey=Env,ParameterValue=prod --region us-east-1
