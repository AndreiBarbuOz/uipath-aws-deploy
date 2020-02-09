# Deployment pipeline for UiPath Orchestrator on AWS



## Deployment

```cmd
aws cloudformation create-stack --stack-name orch-deploy --template-body file://orch-deploy.yaml --parameters file://orch-deploy-params.json --capabilities CAPABILITY_IAM
```

```cmd
aws cloudformation validate-template --template-body file://orch-deploy.yaml --parameters file://orch-deploy-params.json 
```


## Implementation

The template deploys a CodePipeline which, in turn, deploys and then tests a CFN template for the UiPath Orchestrator. The pipeline is triggered by a GitHub webhook. 