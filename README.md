Para funcionar deve ser criado uma library no azure devops contendo os seguintes secrets:

acrLogin = usuario de login no seu acr
containerRegistry = endereço do seu container registry

Dentro do arquivo 01_kubernetes_aks/app-deploy.yaml, altere a linha 24 com o nome endereço do seu container register ex: {{meucontainer.azurecr.io}}/web-game:tag

Em pipelines/azurepipelines.yaml altere a linha 17 e 27 com a sua service connection

Em templates/template-kubernets-build.yaml altere a linha 19 com o valor de seu resource group e altere a linha 20 com o nome de seu cluester kubernets.

Após é só rodar e acessar o game usando o endereço de ingress do loadbalancer