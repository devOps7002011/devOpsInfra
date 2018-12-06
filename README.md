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
 
 fly -t <target> unpause-pipeline -p pipeline_name
 
 6. Open: localhost:8080 - kjør infra jobb
 
 
## Oppgaver

### Basis Pipeline
- Hadde problemer med "permission denied" i concourse pipeline fra både task.sh og
terraform.sh, det løses ved å kjøre følgende kommandoer i tilhørende mappe:
sudo git update-index --chmod=+x task.sh
sudo git update-index --chmod=+x terraform.sh

###  Docker 
Dockerfil bygger container Image av applikasjonen
- Hadde problem i forhold til mappestruktur i applikasjons-repo hvor dockerfile til applikasjon,
ikke ligger i rotmappe, jeg prøvde å søke meg opp på mulige måter å løse dette på,
enten ved å bygge en task-job i concourse som kjørte docker-compose.yml (ligger i prosjekt-mappe)som igjen bygger dockerfilen 
tilhørende applikasjonen, eller kjøre til riktig path fra rot-mappe, sistnevnte fungerte for meg. Sjekk din mappestruktur/eventuelt
endre Dockerfile 



### Google C
 
 
    
 
