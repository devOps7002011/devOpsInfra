# PGR301 - EKSAMENSOPPGAVE - DEVOPS


## GITHUB-REPO
 Infra:
 https://github.com/devOps7002011/devOpsInfra
 
 Applikasjon: 
 https://github.com/devOps7002011/devOpsApp

## Run project
Prosject er basert på at du har Docker

 1. fork github-repo Infra og Applikasjon
 
 2. Opprett en "credentials.yml" basert på samme oppsett som i
    "credentials_example.yml"
    
 3. Endre til egne variabler/id i
 - /concourse/pipeline.yml
 - /terraform/provider_heroku.tf
 - /terraform/statuscake.tf (username)
 
 4. Push til Github 
 
 5. I root infra-prosjekt, kjør:
 
 fly -t ≤target> sp -p pipeline_name -c concourse/pipeline.yml -l credentials.yml
 
 fly -t tutorial unpause-pipeline -p pipeline_name
 
 
 
 
    
 
