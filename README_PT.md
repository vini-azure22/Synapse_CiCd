## Escolha o idioma / Choose the language
- [Português (BR)](README_PT.md)
- [English](README_EN.md)


## Implementação de esteira CI/CD (Integração contínua/Entrega contínua)
<p align="justify"> CI/CD é um termo abrangente que cobre várias fases do DevOps. CI (integração contínua) é a prática de integrar alterações de código em um repositório várias vezes ao dia. CD tem dois significados: a entrega contínua automatiza as integrações de código, enquanto a implementação contínua libera automaticamente as compilações finais para os usuários finais. Os testes frequentes de CI/CD reduzem erros e defeitos de código, tornando-os essenciais para todo fluxo de trabalho de fluxo de trabalho.</p>

## Conteúdos do documento
  * Autores
  * Visão Geral
  * Pré-requisitos
  * Configuração
  * Uso
  * Licença

## Autores:
Vinícius Peters<br>

## Visão Geral
<p align="justify">A implementação do pipeline CI/CD é necessária para agilizar e padronizar a estrutura do seu ambiente, garantindo a qualidade do código desde o ambiente de desenvolvimento até a sua implementação no ambiente de produção, o que é feito automaticamente após a aprovação dos artefatos. Este documento contém o procedimento para implementar essa estrutura de CI/CD usando o Github Actions e o ambiente Azure.</p>

## Pré-requisitos:
* Ter um usuário de serviço com permissão de acesso ao Synapse.
* Conta no GitHub com um repositório criado.
* Permissão de LEITOR no grupo de recursos.
* Permissão de CONTRIBUIDOR no Synapse-Production.
* Conceder permissão do Service Principal.
* Ter um ambiente Synapse de Desenvolvimento (DEV) e Produção (PROD).

## Configuração
### Arquivo readme.yml
<p align="justify">Em seu repositório Github na aba Code, aperte em <strong>creating a new file</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/8c8d9fec-6558-46de-bd87-b242761201b2">
</kbd>
<br><br><br>
<p align="justify">No caminho de pastas, crie um arquivo chamado <strong>readme.yml</strong> na seguinte estrutura <strong> ".github/workflows/readme.yml"</strong>. Após feito isso, aperte em <strong>Commit Changes...</strong></p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/458bf186-78cd-4342-a029-c3104fbe7d0d">
</kbd>
<br><br><br>

### Vincular o Synapse com o Github
<p align="justify">Abra o Synapse DEV e nos ícones à esquerda selecione <strong>Manage</strong> e em seguida, clique em  <strong>Git configuration</strong>. Feito isso, no meio da tela, selecione a opção de <strong>Configure</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/37c1f94b-42c6-4e83-a255-68ba541a3bdd">
</kbd>
<br><br><br>
<p align="justify">Em <strong>Repository Type</strong>, selecione o GitHub e em <strong>Github repository owner</strong> coloque o nome do proprietário da conta.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/f1bb8a5c-6386-47f1-b810-8bffa2295fc0">
</kbd>
<br><br><br>
<p align="justify"> Em <strong>Repository name</strong>, selecione o repositório desejado. Para os demais campos, deixe como está e em seguida aperte em <strong>Apply</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/1cfc4ead-533c-495e-b3c8-ae4f6ffb4797">
</kbd>
<br><br><br>

### Criando uma Branch
<p align="justify">No canto superior esquerdo, clique em <strong>New Branch[Alt+N]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b6eae871-548d-45b0-9d9b-b830867b136e">
</kbd>
<br><br><br>

<p align="justify">Coloque um nome para sua branch e crie baseada na main conforme o exemplo abaixo. Em seguida, aperte em <strong>Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/85476c8e-564d-45ab-8e91-5cc8b19a8746">
</kbd>
<br><br><br>

### Workspace_publish
<p align="justify">A branch workspace_publish será criada automaticamente após ser feito uma publicação no Synapse DEV. Para isso, vamos fazer uma publicação na mesma branch que você acabou de criar! Abra uma pipeline com uma atividade <strong>Set variable</strong> e crie uma variável. Após criado, aperte em <strong>Commit all</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/0309cb13-331f-4177-ad67-69c03766dbc2">
</kbd>
<br><br><br>

Aperte em <strong>OK</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/f0dff78e-d2dc-4496-9cb3-ddf9050ba184">
</kbd>
<br><br><br>
<p align="justify">Feito isso, precisará ser criado um <strong>Pull Request</strong>. Para isso, clique no nome da sua branch no canto superior esquerdo e procure por <strong>Create pull request[Alt+P]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/4e40305d-5c04-4f8c-b086-7a875a8875db">
</kbd>
<br><br><br>
<strong>OBS: Nos passos a seguir, só é possível aprovar um pull request caso você seja o aprovador. Caso contrário, faça uma requisição para o aprovador.</strong>
<br><br>
<p align="justify">Abra seu repositório Github, clique em <strong>Create pull request</strong> ou <strong>Compare & pull request</strong> como mostra a imagem abaixo.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/7baaf7ee-e2a5-47c4-8b67-e813bc5bdb91">
</kbd>
<br><br><br>

<p align="justify">Vai abrir uma aba Open a pull request. Clique em <strong>Create pull request</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/cffdd34b-75ad-4015-872f-bb0e1da90c16">
</kbd>
<br><br><br>

<strong>Merge pull request</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/77176f83-e2bf-417d-b7d6-7294fd7187d8">
</kbd>
<br><br><br>

<strong>Confirm merge</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/d495a227-b8f8-4a44-b94b-a474a15047c3">
</kbd>
<br><br><br>

Agora, abra sua <strong>main branch</strong> e clique em <strong>Publish</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5af27bb7-0c7a-406b-8a7a-58ca23d0a5b5">
</kbd>
<br><br><br>

### Configurações Repositório Github

<p align="justify">Dentro do seu repositório do GitHub, selecione a aba <strong>Code</strong> e procure por <strong>workspace_publish</strong>. Crie um caminho de pastas seguindo este padrão: <strong>.github/workflows/syn-deploy.yml</strong></p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/6d37a2f2-c0ba-4598-bee4-4a0178e769b8">
</kbd>
<br><br><br>
<p align="justify"> E no final deve ser colocado o arquivo com os parâmetros de ambiente, no caso o arquivo <strong>syn-deploy.yml</strong> deve ser posto seguindo o path da imagem mostrada acima.</p>


### Configurando arquivo syn-deploy.yml
<p align="justify">Dentro do arquivo <strong>syn-deploy.yml</strong>, você deve adequar as três linhas <strong>TemplateFile,ParametersFile e OverrideArmParameters</strong> com o nome do seu workspace, como mostra na imagem abaixo destacado em vermelho. Observe que, o arquivo contém linhas que serão valores herdados do Github Secrets(considere os que estão com "${{secrets.____}}). Esses serão os secrets que terão que ser atribuídos no Github.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/a1db97c6-ee99-4518-bee0-01c1538be158">
</kbd>
<br><br><br>
Esses serão os parâmetros que serão herdados no Github: 

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/3d0cc300-90c0-4a60-8687-7974e15ea677">
</kbd>
<br><br><br>

### Configurando Secrets Github

Vá em <strong>Settings</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/430172cd-0aa1-49ca-b124-6b21e06da60b">
</kbd>
<br><br><br>
<p align="justify">Ao lado esquerdo da tela, vá em <strong>Secrets and variables</strong> e <strong>Actions</strong>. Na aba <strong>Secrets</strong>, selecione <strong>New repository secret</strong>. Nesse repositório que será atribuído o valor das variáveis que serão herdadas no arquivo <strong>syn-deploy.yml</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/862df26c-21c7-4042-a1a4-6eb939f36ada">
</kbd>
<br><br><br>
<strong>Vale ressaltar que todos esses parâmetros devem ser preenchidos com os dados do ambiente de Produção.</strong>

Atribua o nome do secret e o valor. Nesse caso, será atribuído para cada um desses:

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

Exemplo:<br>
<strong>Name</strong> = WORKSPACENAME<br>
<strong>Secret</strong> = nome do seu workspace<br>

Em seguida, clique em <strong>Add secret</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/28f720e4-f015-468f-b9a2-d86a6f9de088">
</kbd>
<br><br><br>

### Como encontrar cada um dos parâmetros

Para os parâmetros:<br>
* <strong>WORKSPACENAME</strong><br>
* <strong>RESOURCEGROUP</strong><br>
* <strong>SUBSCRIPTIONID</strong><br>

<p align="justify">No portal Azure, procure pelo seu Synapse workspace de produção. Na aba da esquerda ao lado, vá em <strong>Overview</strong> e encontrará as informações dos três parâmetros listados acima.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/44f345af-3469-45a3-8ef2-728bc970378e">
</kbd>
<br><br><br>
Para os parâmetros :

<strong>CLIENTID</strong><br>
<strong>CLIENTSECRET</strong><br>
<strong>TENANTID</strong><br>

<p align="justify">Deverá ser criado um Service Principal.Na barra de pesquisa digite <strong>App Registrations</strong> e selecione.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/874f9d93-f936-49cc-b393-8f909ab473f3">
</kbd>
<br><br><br>
Feito isso, clique em <strong>+New registration</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/d4d36c8e-b861-474b-897b-232bba9a14c3">
</kbd>
<br><br><br>
Após isso, atribua um nome qualquer e aperte em <strong>Register</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/3bd0606b-3133-4f94-a2cc-7899ed96fb85">
</kbd>
<br><br><br>

<p align="justify">Após criado, você será levado para a página <strong>Overview</strong> do Service Principal. Aqui, você encontrará o <strong>CLIENTID</strong> e <strong>TENANTID</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/dae17adb-f935-4e4e-8893-1e0b3df5920e">
</kbd>
<br><br><br>
<p align="justify">Para o <strong>CLIENTSECRET</strong>, na barra de opções lateral esquerda selecione a opção <strong>Certificates & secrets</strong>. Após isso, clique em <strong>+ New client secret</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b26adf1e-5f56-4168-9f23-016cbe8a2457">
</kbd>
<br><br><br>
<p align="justify">Em <strong>Description</strong> coloque uma descrição qualquer ou um nome. Em seguida, clique em <strong> Add </strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5456a185-9831-4e96-b58b-36de8ce41e82">
</kbd>
<br><br><br>
<p align="justify">Após criado aparecerá na coluna <strong>Value</strong> o valor do <strong>CLIENTSECRET</strong>. Grave esse valor, pois ele <strong>só aparecerá uma vez e não será possível ver novamente!</strong></p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b6962899-ed70-4051-9b61-0cc058093254">
</kbd>
<br><br><br>

### Atribuindo permissões ao Service Principal

<p align="justify">Com todos os parâmetros preenchidos dos passos anteriores, entre no seu workspace do Synapse de <strong>Produção</strong> e vá nas opções de <strong>Access Control(IAM)</strong> e clique em <strong>Role assignment</strong>. Procure mais acima a opção <strong>+ Add</strong>. </p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/91469a4b-e253-4650-9e75-f406c3a3c67e">
</kbd>
<br><br><br>
<p align="justify">Será atribuído a permissão de <strong>Reader</strong> do Service Principal ao resource group de produção. Para isso, selecione a primeira opção de Reader e em seguida em <strong>Next</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/702faa15-d876-4d0e-9942-d80aad982b01">
</kbd>
<br><br><br>
<p align="justify">Na aba Members, clique na opção <strong>+ Select members</strong>. Utilize a barra de pesquisa ao lado para escolher o usuário e clique em <strong>Select</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/a60ace36-9ff5-4fa8-ba0d-1d2ecf461a72">
</kbd>
<br><br><br>
Feito isso, clique em <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/6bac5d72-e8c6-4fd9-bbbc-ed244956aa88">
</kbd>
<br><br><br>
<p align="justify">Dado a permissão de Reader, repita o passo anterior, mas agora dê a permissão de <strong>Contributor</strong> ao workspace de produção. Clique novamente em <strong>Role Assigment</strong> e depois em <strong>+Add</strong>. Selecione a aba Privileged Admnistrator roles, e clique em <strong>Contributor</strong>. Em seguida, aperte em <strong>Next</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/e1c1db92-0fee-4c87-9eab-99f1c5a3b1c2">
</kbd>
<br><br><br>
<p align="justify"> Em Members, clique em em <strong>+Select members</strong> e selecione o usuário para aplicar a permissão de <strong>Contributor</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/4040398a-e1ef-488e-bd52-077ec49819d1">
</kbd>
<br><br><br>
Clique em <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/0629429c-3868-4f6a-9749-171204867430">
</kbd>
<br><br><br>
Por fim, abra o Synpase Studio do Synapse de Produção.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5d757a3c-2ff6-429d-93f2-04be234c528b">
</kbd>
<br><br><br>
<p align="justify">Vá até a opção <strong>Manage</strong> na lateral esquerda e <strong>Access control</strong>. Clique em <strong>+ Add</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/bdb79faa-e708-4e22-9381-47d1c8d86374">
</kbd>
<br><br><br>
<p align="justify">Selecione a função <strong>Synapse Artifact Publisher</strong>. Na barra de baixo você deve selecionar o usuário Service Principal anteriormente criado e clicar em <strong>Apply</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/ca292ec5-8f1b-49c5-8d8b-e8a5fe8db85b">
</kbd>
<br><br><br>

### Configurar Azure Key Vault

<strong>Deverá ser criado um Key vault para os dois ambientes DEV e PROD.</strong>

No portal Azure, vá até a barra de pesquisa e digite por <strong>Key Vaults</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b2512f47-2b02-4960-8622-6c012d820d1b">
</kbd>
<br><br><br>
Clique em <strong>+Create</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/8845731d-e5ab-407f-bd7f-822e70e7398b">
</kbd>
<br><br><br>
<p align="justify">Após isso, preencha as informações de criação do key vault atribuindo o resource group que foi criado no Synapse de Produção. Em seguida, vá até <strong>Review+Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/fc74c4e3-1903-46e7-99f2-ab79b12016c0">
</kbd>
<br><br><br>
<p align="justify">No Key Vault de produção, clique na lateral esquerda em <strong>Access Control(IAM)</strong>, clique em <strong>+Add</strong>e <strong>Add role assignment</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/1973a791-e2ef-419e-8b50-f1a4a032b977">
</kbd>
<br><br><br>
Em <strong>Role Assignments</strong> procure por <strong>Key Vault Secrets Officer</strong>. Em seguida, clique em <strong>Next</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/d7ce34e8-d6ec-4808-ad38-66dc2cab74b3">
</kbd>
<br><br><br>
<p align="justify">Feito isso, vá em Members e na opção <strong>Assign access to</strong> selecione <strong>Managed identity</strong>. Depois de selecionado, clique em <strong>+Select Members</strong>.</p>

Em <strong>Managed Identity</strong> selecione Synapse workspace(). Depois disso, selecione seu ambiente Synapse de Produção.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/3558faa7-475d-42e0-a39d-69a8b9de4533">
</kbd>
<br><br><br>

### Configurar Linked Service

Em seu Workspace de DEV, vá até <strong>Manage/<strong> e <strong>Linked services</strong>. Clique em <strong>+ New</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/5a679cf7-4de5-4a6a-8d6e-3d917286f6f5">
</kbd>
<br><br><br>
Na barra de pesquisa pesquise por <strong>Azure Key Vault</strong> e clique em <strong>Continue</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/b104286e-89bf-4eb6-9c42-43dd03c86717">
</kbd>
<br><br><br>
<strong>Nome:</strong> Atribua um nome para o Key Vault.<br>
<strong>Assinatura do Azure:</strong> Selecione sua assinatura.<br>
<strong>Nome do Azure Key Vault:</strong> Selecione o Key Vault criado do ambiente de produção.<br>

Para os demais, deixe padrão. Após isso, aperte em <strong>Commit</strong>.

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/9798d961-e003-437b-ab52-3418801650e7">
</kbd>
<br><br><br>
<p align="justify"> O próximo passo você precisará publicar algo novamente em DEV com o Linked Service devidamente criado( repita o passo do tópico Workspace_publish).</p>


<p align="justify">Após isso você deverá entrar em seu arquivo <strong>TemplateWorkspace.json</strong> e buscar o nome do KV que foi gerado automaticamente como mostra abaixo:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/6e5ec722-dffe-4d55-93dd-d54bc019333c">
</kbd>
<br><br><br>
<p align="justify"> Copie o "LS_KV_DEV_properties_typeProperties_baseUrl" e o <strong>defaultValue</strong>. Eles serão utilizados no próximo passo para a criação do arquivo <strong>ParameterPRD.json</strong>.

### Criando arquivo ParameterPRD.json

<p align="justify"> No seu repositório Github, crie um arquivo chamado <strong>ParameterPRD.json</strong> dentro da pasta do seu workspace de DEV e cole os parâmetros copiados anteriormente no seguinte formato:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/ea247b74-ef31-4cd2-8f02-db88b4a687c4">
</kbd>
<br><br><br>
<p align="justify"> O nome do arquivo <strong>ParameterPRD.json</strong>, certifique-se de que o seja exatamente igual ao nome que está no arquivo <strong>syn-deploy.yml</strong> em <strong>OverrideArmParameters</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/a444a571-a19d-4a5d-a6c6-2a7f6bb9ef47">
</kbd>
<br><br><br>

## Uso

<p align="justify"> Em sua branch no ambiente de Desenvolvimento caso haja mudanças, o processo para levar para <strong>produção</strong> irá seguir esses passos:</p>

<p align="justify"> Realize um <strong>commit</strong> com suas mudanças. No exemplo abaixo, iremos utilizar a "Pipeline 2" na branch produto:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/ea4ee1d9-f5d6-40fe-aaff-9fe60319c172">
</kbd>
<br><br><br>
<p align="justify"> Crie um <strong>Pull request</strong> para branch principal. No exemplo é a main branch</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/39fdce80-ef09-4dc4-96b2-fff79d89f8bb">
</kbd>
<br><br><br>
<p align="justify"> Após ter seu <strong>Pull request aprovado</strong>, a main branch irá possuir todas as suas alterações. Portanto, o responsável pelo Pull Request, deverá clicar em Publish como mostra a imagem abaixo:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/446f7b39-5895-4bea-bc40-59dc0f33143d">
</kbd>
<br><br><br>
<p align="justify"> Aguarde até que a mensagem de sucesso apareça em sua tela:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/61eaaf62-8bbf-4f6f-8d36-c33040784d6a">
</kbd>
<br><br><br>
<p align="justify"> Após isso, entre no ambiente de <strong>produção/<strong> e você verá suas alterações no ambiente de produção:</p>

<kbd>
<img alt="image" src="https://github.com/brunoandrade7771/Synapse-teste-cicd/assets/145786554/2285cf81-68b5-4c93-a704-1defcd49571d">
</kbd>
<br><br><br>
Esteira CI/CD finalizada!
