# Jogo 2048 com Integração GitHub, Azure DevOps e AKS 🎮🚀

Este projeto implementa o popular jogo **2048** utilizando **JavaScript**, **CSS** e **SCSS**, com deploy automatizado em um cluster **Azure Kubernetes Service (AKS)**. A integração contínua é gerenciada pelo **Azure DevOps (ADO)**, demonstrando habilidades em DevOps e desenvolvimento full-stack.

---

## 🛠️ Funcionalidades

- **Jogo 2048 Interativo:** Interface responsiva para jogar o clássico 2048.
- **Pipeline CI/CD Automatizado:** Build e deploy automáticos via Azure DevOps.
- **Deploy em AKS:** Aplicação containerizada e orquestrada no Azure Kubernetes Service.
- **Integração com Azure Container Registry (ACR):** Armazenamento seguro das imagens Docker.

---

## 📋 Pré-requisitos

- **Conta no Azure:** Com permissões para criar recursos como AKS e ACR.
- **Azure DevOps Configurado:** Com acesso ao repositório GitHub.
- **Service Connection no Azure DevOps:** Para integração com o Azure.
- **GitHub Actions (Opcional):** Para integração contínua alternativa.

---

## 🚀 Como Configurar e Executar o Projeto

1. **Clone o Repositório:**

   ```bash
   git clone https://github.com/jeffersonvalente/2048game.git
   cd 2048game
   ```

2. **Configurações no Azure DevOps:**

   - **Variáveis de Biblioteca:**
     - Crie uma biblioteca no Azure DevOps com os seguintes secrets:
       - `acrLogin`: Usuário de login no Azure Container Registry.
       - `containerRegistry`: Endereço do seu container registry (ex: `meucontainer.azurecr.io`).

   - **Arquivo de Deploy:**
     - No arquivo `01_kubernetes_aks/app-deploy.yaml`, altere a linha 24 com o endereço do seu container registry:
       ```yaml
       image: {{meucontainer.azurecr.io}}/web-game:tag
       ```

   - **Pipeline Azure Pipelines:**
     - Em `pipelines/azurepipelines.yaml`, altere as linhas 17 e 27 com o nome da sua service connection.

   - **Template de Build:**
     - Em `templates/template-kubernets-build.yaml`, ajuste:
       - Linha 19: Nome do seu resource group.
       - Linha 20: Nome do seu cluster Kubernetes.

3. **Executar o Pipeline:**
   - Após as configurações, execute o pipeline no Azure DevOps para buildar e deployar a aplicação.

4. **Acessar o Jogo:**
   - Após o deploy, acesse o jogo através do endereço de ingress do load balancer configurado no AKS.

---

## 🗂️ Estrutura do Projeto

- `01_kubernetes_aks/`: Configurações de deploy no AKS.
- `pipelines/`: Arquivos de pipeline para Azure DevOps.
- `templates/`: Templates reutilizáveis para build e deploy.
- `README.md`: Documentação do projeto.

---

## 📈 Benefícios Técnicos

- **Automação Completa:** Pipeline CI/CD automatizado com Azure DevOps.
- **Escalabilidade:** Deploy em AKS garante alta disponibilidade.
- **Segurança:** Imagens armazenadas de forma segura no Azure Container Registry.
- **Integração Contínua:** Integração perfeita entre GitHub, Azure DevOps e Azure.

---

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests com sugestões de melhorias ou correções.

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 📞 Contato

Para dúvidas ou suporte, entre em contato:

- **Autor:** Jefferson Valente
- **LinkedIn:** [jefferson-hoy-valente](https://www.linkedin.com/in/jefferson-hoy-valente/)

