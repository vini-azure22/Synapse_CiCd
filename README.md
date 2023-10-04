# Synapse_CiCd

# Implementação de esteira CI/CD (Integração contínua/Entrega contínua)
<p align="justify"> CI/CD é um termo abrangente que cobre várias fases do DevOps. CI (integração contínua) é a prática de integrar alterações de código em um repositório várias vezes ao dia. CD tem dois significados: a entrega contínua automatiza as integrações de código, enquanto a implementação contínua libera automaticamente as compilações finais para os usuários finais. Os testes frequentes de CI/CD reduzem erros e defeitos de código, tornando-os essenciais para todo fluxo de trabalho de fluxo de trabalho.</p>


## Conteúdos do documento
  * Autores
  * Visão Geral
  * Pré-requisitos
  * Configuração
  * Uso
  * Licença

## Autores:

Bruno Andrade<br>
Raphael Freixo<br>
Vinícius Peters<br>

## Visão geral
<p align="justify">A implementação da esteira CI/CD é necessária para agilizar e padronizar a estrutura de seu ambiente, garantindo a qualidade dos códigos no ambiente de desenvolvimento até sua implementação no ambiente de produção, que é realizada automaticamente após a aprovação dos artefatos.
Nesse documento contém o procedimento para implementar essa estrutura de CI/CD utilizando Github Actions e o ambiente Azure.</p>

## Pré-requisitos:

* Possuir usuário de serviço com permissão de acesso ao synapse;
* Conta no github com repositório criado;
* Permissão de READER ao resource group;
* Permissão de CONTRIBUTOR ao Synapse-Production;
* Conceder permissão do Service Principal;
* Possuir ambiente Synapse de Desenvolvimento(DEV) e produção(PROD);<br><br>

## Configuração Github:
<p align="justify"> No seu repositório Github, aperte em <strong>creating a new file<strong>.</p>
<kbd>
<br><br>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/2bcd8beb-74ce-44de-b009-942da3b396f7">
</kbd>
<br><br><br>
<p align="justify"> No caminho de pastas, crie um arquivo chamado "readme.yml" na seguinte estrutura de pasta ".github/workflows/readme.yml". Após feito isso, aperte em <strong>Commit Changes...<strong></p>
<kbd>
<br><br>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/209a8179-1f60-4bdf-9296-83b945302282">
</kbd>
<br><br><br>
<p align="justify">
1) Vincular ambiente ao git-hub actions: Abra o Synapse-DEV, selecione a opção <strong>MANAGE</strong> e em seguida a ultima opção de git-configuration, como mostra a imagem abaixo:</p>
<br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/73370525-6b2a-4296-845d-fd1a42bec98e">
</kbd>
<br><br>

Em seguida, selecione o botão **Configurar** no meio da tela.
<br><br>

2) Em **Tipo de Repositório**, selecionar **GitHub** e em seguida colocar o nome do proprietário da conta:
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/4ee41b11-3399-4efa-886c-7212d6c1cbe7">
</kbd>
<br><br>

3) Selecionar o repositório desejado e todos os campos serão preenchidos automaticamente. Não mexa em nenhuma configuração e aperte em <strong>Apply.</strong><br>

<br><br>

<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/7c0df6f0-4302-42fc-bcd6-fd04bb5537b3">
</kbd>
<br><br>

Para criar uma nova branch, no canto superior esquerdo clique em <strong>main branch</strong> e em seguida clique em <strong>New Branch[Alt+N]</strong>.
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/df7cc483-ac19-449d-8fac-f763ecfc1e06">
</kbd>
<br><br>
Coloque um nome para sua branch e crie conforme o exemplo abaixo. Em seguida, aperte em <strong>Create</strong>.
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/c2eb2066-48b3-47d9-a3df-8d35217d3bc1">
</kbd>
<br><br>
<p align="justify">Para a criação da branch <strong>workspace_publish</strong>, precisamos inicialmente fazer uma publicação no Synapse DEV. Na mesma branch que você acabou de criar, crie uma pipeline com uma atividade <strong> Set variable </strong> e crie uma variável.Após criado, aperte em <strong> Commit all</strong><p> 
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/8f5218fc-bf90-404c-9846-041de95a6b1b">
</kbd>
<br><br>
Após isso, aperte em <strong>OK</strong><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/bcfc6147-3a8d-4983-9672-0e7adfdf3f7c">
</kbd>
<br><br>
<p align="justify">Feito isso, precisará ser criado um Pull Request. Para isso, clique no nome da sua branch criada no canto superior esquerdo e procure por <strong>Create pull request[Alt+P]</strong></p>.
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/78303962-1a98-4a33-935a-fe5ff84eb807">
</kbd>
<br><br>
<p align="justify">Abra seu repositório Github,  clique em <strong> Create pull request</strong> ou <strong>Compare & pull request</strong> como mostra a imagem abaixo:</p>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/ce4c682d-a0ed-4eb4-948c-209e7afcebcd">
</kbd>
<br><br>
Vai abrir uma aba "Open a pull request". Clique em <strong>Create pull request</strong>.
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/f9628d4c-4ab9-4de1-bb6c-4618b811dc55">
</kbd>
<br><br>
<strong>Confirm merge</strong>.<br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/632e7013-3f1a-4c6f-8180-a6dfbf98b5da">
</kbd>
<br><br>
Realizado os passos anteriores, abra agora sua <strong>main branch</strong> e clique em <strong>Publish</strong>.
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/145786554/812bc13a-e59b-4875-951a-9d3646588732">
</kbd>

## Configurações Repositório Github
<p align="justify">Inicialmente, faça uma primeira publicação no ambiente Sinapse DEV para que o Github crie uma branch chamada "Workspace_publish".
Dentro da conta do GitHub,repositório do synapse e do workspace-publish, crie um caminho de pastas seguindo este padrão: .github/workflows/</p>

<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/66cf6c3c-05d4-4301-8a01-449b9ab72fdb">
</kbd>
<br><br>

E no final deve ser colocado o arquivo com os parâmetros de ambiente, no caso o arquivo: syn-deploy.yml deve ser posto seguindo o path da imagem mostrada acima. 


<p align="justify">Dentro do arquivo .yml, você deve adequar as tres linhas "TemplateFile","ParametersFile" e "OverrideArmParameters" com o nome do seu workspace, como mostra na imagem abaixo, destacado em vermelho. Considerando o meu workspace criado, ficou "azure-teste-dev".
Observe que, o arquivo contém linhas que serão valores herdados do Github Secrets(considere os que estão com "${{secrets.____}}).
Esses serão os secrets que terão que ser atribuídos no Github</p>
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/f667ba78-7060-4cea-a2c3-c33ad6bd1c6a">
</kbd>
<br><br>

*Observação*
<p align="justify">A terceira linha mostrada "OverrideArmParameters" não será preciso alterar nesse momento, pois iremos criar esse arquivo mais pra frente, podendo ser ignorada por enquanto.</p>

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

<br><br>
<kbd>
<img width="800" alt="MicrosoftTeams-image(18)" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/c085bbd7-fe34-4997-a51d-a4f1ff465fb8">
</kbd>
<br><br>


<p align="justify">Após isso, vá em **settings**, e ao lado esquerdo da tela, vá em **Secrets and variables>Actions**. Na aba "Secrets", selecione **"New repository secret"**. Nesse repositório que será atribuído o valor das variáveis que serão herdadas no arquivo syn-deploy.yml.</p>
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/a744988a-e72f-4b05-a720-bc482f50bd3c">
</kbd>
<br><br>

Atribua o nome do secret e o valor. Nesse caso, será atribuído para cada um desses:

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

**Exemplo:** <br>
**Name =** 'WORKSPACENAME'<br>
**Secret =** '[nome do seu workspace]'<br>

Em seguida, clique em **Add secret**.<br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/691c3e75-2b2b-4f40-b4ef-4370e9ff4775"><br>
</kbd><br>
**Vale ressaltar que todos esses parâmetros devem ser preenchidos com os dados do ambiente de Produção**.<br>

## Como encontrá-los:
A imagem abaixo mostra como encontrar esses parâmetros no seu workspace:
* WORKSPACENAME
* RESOURCEGROUP
* SUBSCRIPTIONID

Para o SUBSCRIPTIONID você deve abrir seu workspace e logo sem seguida verá o parâmetro:
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/4b24e1df-d45e-4078-9a2a-68f5df4e3089">
</kbd>
<p align="justify">Para o **CLIENTID**, na barra de pesquisa digite App Registrations e clique:</p>
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/2837fd29-dfea-4bdf-ad58-15f1bca46545"><br><br>
</kbd>
<br><br>
Após isso, deve ser criado um usuário que será atríbuido permissões nos próximos passos:<br><br>
<br><br>
<kbd>
<img width="800" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/b20c0112-58c8-4e79-9e71-c353a8ca292a"><br>
</kbd>
<br><br>
Na aba All Aplications, você encontrará o usuário criado e seu **CLIENTID**:<br><br>
<kbd>
<img width="1000" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/647496ae-abd9-4b8e-b361-5133fd89ba52"><br>
</kbd>
<br><br>
Para encontrar o **TENANTID**, basta clicar no usuário criado na etapa anterior. No caso de exemplo, clique em USER-GIT <br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/ee568520-d1e3-489d-980d-fbc1a4a8b037">
</kbd>
<br><br>
Para o **CLIENTSECRET** ainda no passo anterior, na barra de opções lateral esquerda você irá encontrar a opção *Certificates & secrets* e após clicar nessa opção, clique em **+New client secret** e criar uma identidade:
<br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/e519d68a-3a76-4f70-87bf-9282abb17059">
</kbd>
<br>

Coloque uma descrição de sua preferência e no campo abaixo você pode deixar 90 dias por padrão. Após feito isso você pode clicar em *Add* e então voltar para a página anterior:
<br><br>
<kbd>
<img width="1000"  height="500" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/610c3c7e-1c7c-4ade-9aff-cc3ceea9001c">
</kbd>
<br><br>

Com todos os parâmetros preenchidos, entre no seu workspace do Synapse de Produção e vá nas opções de **Access Control(IAM)** e clicar em Role assignment, como mostra a imagem abaixo:

<br><br>
<kbd>
<img width="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/cf32881b-888f-4fe5-b540-4233213000e5">
</kbd>
<br><br>

Selecione a primeira opção de *Reader* e em seguida em *Next*
<br><br>
<kbd>
<img width="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/8fb1e6b7-ef91-4780-8866-68976ceaec79">
</kbd>
<br><br>
Após isso clicar na opção *Select Members* para selecionar o usuário para dar permissão de Reader ao Resource Group:
<br>
<kbd>
<img width="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/ded5985b-e1ae-4bac-9d5a-85d70ab0b71d">
</kbd>
<br><br>

Após criado a permissão de *READER*, abra o Synapse de produção e acesse o Access Control (IAM) exatamente do mesmo jeito do passo anterior, mas agora dando permissão de *Contributor* ao workspace de produção.
Então novamente clicar em *Role Assigment* e depois em *Add* e então selecionar *Privileged Admnistrator roles* como mostra a imagem abaixo:
<br><br>
<kbd>
<img width="2100" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/17ac8e05-548e-441c-ac16-700e4895e228">
</kbd>
<br><br>

Clique em *Select Members* e selecione o usuário para aplicar essa permissão de *Contributor*:
<br><br>
<kbd>
<img width="1000" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/3ad9c74b-584a-46d7-8c26-330fed09ddd3">
</kbd>
<br><br>

Após esses passos, você terá o usuario com permissões de Reader no resource group e Contributor no workspace de produção.

Por ultimo abra o Synapse Studio, acesse a opção **Manage** na lateral esquerda:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/a0778f1c-5cd7-4c39-bafd-4095eaa669ad">
</kbd>
<br><br>

Após isso, vá em **Access control** no menu lateral esquerdo e clicar em **Adicionar** para atribuir a função de **Editor de Artefato** ao usuário anteriormente criado, e na barra de baixo você deve selecionar o usuário que deseja atribuir:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/3437f11a-f249-4ae7-bd22-72c9e5d19ea8">
</kbd>
<br><br>
## Configurar Azure Key Vault
**Deverá ser criado um Key Vault para cada ambiente Synapse DEV e PROD**.

Passo 1: Em sua conta do Synapse, vá até a barra de pesquisa e digite por **Key Vault**, e após isso clique em **Create**
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/aea32c73-2fe9-45eb-a110-48ab4b651220">
</kbd>
<br><br>
Após isso, preencha as informações de criação do key vault atribuindo o resource group que foi criado no Synapse de Desenvolvimento. Em seguida, vá até Next e Review+Create. 
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/a0f521a5-f8f3-4249-96c0-28d95324c963">
</kbd>
<br><br>
Após dar permissão de acesso ao usuário para criar os Secrets dentro do Key-Vault, crie os secrets com o mesmo nome do arquivo .yml dos passos anteriores.(argumentar melhor).
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/8ac96d49-fed9-4748-91bd-32e353bdbe3a">
</kbd>
<br><br>
**Obs: Todo esse passo deve ser feito para ambiente de PRD também, com algumas ressalvas que iremos ver logo a baixo.**


Para o ambiente de produção você deve seguir os passos a seguir:
 
Ir no Key Vault, clicar na lateral esquerda em **Access Control(IAM)** e em seguida abra **Role Assignments** e procure por **KEY VAULT SECRETS OFFICER**. Em seguida, clique em Next:
<br><br>
<kbd>
<img width="1600" height="900" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/c4b6a4d2-ec4e-4dda-b556-a6558701b14b">
</kbd>
<br><br>
Feito isso, vá em **Members** e na opção **Assign access to** selecione **"Managed identity"**. Depois de selecionado, clique em **+Select Members**.
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/1eee6650-428e-4f7d-8938-018bfe8ae37c">
</kbd>
<br><br>
Selecione sua subscription. Em **Managed Identity** selecione Synapse workspace(). Depois disso, selecione seu ambiente Synapse de Produção.
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/102155624/88f5b025-1cc9-4a15-9067-27d47966a824)">
</kbd>
<br><br>

Agora sua permissão foi atribuida ao ambiente de produção.

O proximo passo você precisa publicar algo novamente em DEV com o KV devidamente criado. Após isso você deverá entrar em seu arquivo TemplateWorkspace e 
buscar o nome do KV que foi gerado automaticamente (geralmente ele é criado na linha 20) como mostra abaixo:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/5e431ae6-8f16-4de0-b4d4-d98653faceb9">
</kbd>
<br><br>
Após encontrar esses parametros, crie um arquivo chamado ParameterPRD.json dentro da pasta do seu workspace de DEV e cole esses parametros no formato chave-valor:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/971224ab-0932-41ca-9363-bb2fc46a809c">
</kbd>
<br><br>
Após feito isso, você devera voltar no seu arquivo .yaml e na linha de "OverrideArmParameters" e você devera preenchê-lo com o nome de seu workspace e o nome do arquivo que voce criou chamado: ParameterPRD.json assim como mostra a imagem abaixo:
<br><br>
<kbd>
<img width="600" alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/36ea49af-9b94-4716-94a3-989a24090f23">
</kbd>
<br><br>

## Usabilidade
Em sua branch no ambiente de Desenvolvimento após existir mudanças, o processo para levar para produção ira seguir esses passos:
1) Realize um commit com suas mudanças. No exemplo abaixo, iremos utilizar a "Pipeline 2" que não existe em produção:
<br><br>
<kbd>
<img width="587" alt="imagem1" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/30d26293-38b7-444c-8700-d30f4635f8d8">
</kbd>
<br><br><br>
2) Crie um pull request para branch principal. No exemplo é a "main branch": 
<br><br>
<kbd>
<img width="202" alt="MicrosoftTeams-image (40)" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/87d75eeb-ae2c-4c42-b63e-62ec5de195fa">
</kbd>
<br><br><br>
3) Após seu Pull Request ser aprovado, a "main branch" ira possuir todas as suas alterações. Portanto, o responsável pelo Pull Request, deverá clicar em Plublicar como mostra a imagem abaixo:
<br><br>
<kbd>
<img width="310" alt="IMAGEM3" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/00ed549b-3752-4a26-a5d2-05dbecb80805">
</kbd>
<br><br><br>
4) Aguarde até que a mensagem de sucesso apareça em sua tela:
<br><br>
<kbd>
<img width="957" alt="IMAGEM4" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/90c860d6-0638-4854-afb7-aac06e062e5a">
</kbd>
<br><br><br>
5) Após isso, entre no ambiente de produção e você verá suas alterações no ambiente de produção:
<br><br>
<kbd>
<img width="400" alt="IMAGEM5" src="https://github.com/vini-azure22/Synapse_CiCd/assets/141336497/cb77a586-d007-4661-8598-918092041f05">
</kbd>
<br><br><br>

## Estrutura do projeto


<br><br><br>
## Licença

Este projeto é disponibilizado sob os termos da Licença MIT.

Direitos autorais 2023 Ernst & Young (EY)

A permissão é concedida, gratuitamente, a qualquer pessoa que obtenha uma cópia deste software e dos arquivos de documentação associados (o "Software"), para tratar o Software sem restrições, incluindo, sem limitação, os direitos de usar, copiar, modificar, mesclar, publicar, distribuir, sublicenciar e/ou vender cópias do Software, e permitir que as pessoas a quem o Software seja fornecido façam isso, sujeitas às seguintes condições:

O aviso de direitos autorais acima e este aviso de permissão devem ser incluídos em todas as cópias ou partes substanciais do Software.



